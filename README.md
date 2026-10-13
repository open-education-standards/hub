# OES Hub

The official public hub for [OES](https://open-education-standards.github.io/oes/)
content, at **https://open-education-standards.github.io/hub/**.

Anyone can browse it, and any OES app can import from it: add
`https://open-education-standards.github.io/hub/index.json` as a hub. It
is a set of static files, built from this repository by
[`oes-hub`](https://github.com/open-education-standards/oes-tooling/tree/main/packages/hub).
How hubs work is specified in OPK's [Hubs](https://open-education-standards.github.io/oes/specs/opk/hubs) page.

## Publish a package

1. Put your content in a public GitHub repository with an OPK
   `package.json` at its root (or in a subfolder; see `path` below). Its
   `name` must be `{your-github-name}/{package}`.
2. Tag a release, e.g. `v1.0.0`. The version published is the one in
   `package.json`.
3. Open a pull request adding `packages/{your-github-name}/{package}.yml`:

   ```yaml
   source: https://github.com/{your-github-name}/{repo}
   path: .            # optional: the package's folder in the repo
   versions:
     - tag: v1.0.0
   ```

The pull request is checked automatically: the release is fetched,
validated, linted and bundled, and any problem is reported on the pull
request. Once it is merged, the version is published.

To publish a new version, tag it in your repository and add the tag to
`versions` in another pull request.

## Rules

- **Your namespace is your GitHub name.** A package's namespace must
  equal the GitHub owner of its source repository.
- **Published versions never change.** Once a version is published it is
  kept exactly as it was, even if the tag moves or the repository is
  deleted. To change something, publish a new version.
- **Bad versions are yanked, not deleted.** Add `yanked: <reason>` under
  the tag. The version leaves browsing but stays available to anyone
  already using it.
- **Everything here is public**, including any answer-key files in a
  package. Don't publish graded content that has to stay secret.
- **Content must be yours to share**, under the licence you state in
  `package.json`.

`store/` holds every published version and is written only by the build.
Pull requests that change it are rejected.

## Run your own hub

Use [`hub-template`](https://github.com/open-education-standards/hub-template)
to start a hub of your own, for a school, a team or a subject.

