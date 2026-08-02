# Apache ECharts

Apache ECharts is a free, powerful charting and visualization library offering
easy ways to add intuitive, interactive, and highly customizable charts to your
commercial products. Read more at the website: <https://echarts.apache.org/>

This repository is the ThingsBoard-maintained fork of
[Apache ECharts](https://github.com/apache/echarts), consumed by the ThingsBoard
platform as a GitHub archive tarball. Fork releases are tagged with a `-TB`
version suffix and differ from the upstream 5.5.1 release as follows:

+ `package.json` additionally exports the internal `lib/coord/axisHelper` module
  and resolves `zrender` to the
  [ThingsBoard fork of zrender](https://github.com/thingsboard/zrender), which
  carries a pointer-transformer fix on top of the upstream zrender 5.5.0 release.
+ `index.d.ts` replaces the export assignment with re-exports for TypeScript ESM
  compatibility; the file carries its own modification notice.
+ The `lib` and `dist` build outputs, which upstream generates only when
  publishing to npm, are committed (and un-ignored in `.gitignore`) so that the
  GitHub archive tarball installs the way the npm package would. The `dist`
  bundles are rebuilt from this fork and therefore include the modified zrender.

The list above serves as the modification notice required by section 4(b) of the
Apache License 2.0 for the changed files that cannot carry an in-file notice,
such as the JSON manifests and the generated bundles.

## License

ECharts is licensed under the Apache License, Version 2.0. See
[LICENSE](LICENSE) for the full license text.

The attribution notices of the original work are preserved in the
[NOTICE](NOTICE) file, and the bundled third-party work is credited in the
`licenses` directory.
