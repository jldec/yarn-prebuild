# yarn-prebuild
For testing Gitpod incremental prebuilds with yarn.

- Create a project with this repo and turn on incremental prebuilds in the project settings.
- The first prebuild should run a full `yarn install` and take about a minute.
- Dependencies should remain available to subsequent prebuilds without reinstalling. 

What appears to be correct behavior was observed and saved in the prebuild-log files

#### How this repo was created
(starting from an empty repo in Gitpod)
```
gitpod /workspace/yarn-prebuild (main) $ which yarn 
/home/gitpod/.nvm/versions/node/v16.15.0/bin/yarn
gitpod /workspace/yarn-prebuild (main) $ yarn --version
1.22.18
gitpod /workspace/yarn-prebuild (main) $ yarn init -y
yarn init v1.22.18
warning The yes flag has been set. This will automatically answer yes to all questions, which may have security implications.
success Saved package.json
Done in 0.07s.
gitpod /workspace/yarn-prebuild (main) $ cat package.json 
{
  "name": "yarn-prebuild",
  "version": "1.0.0",
  "main": "index.js",
  "repository": "https://github.com/jldec/yarn-prebuild.git",
  "author": "Jurgen Leschner <jldec@ciaosoft.com>",
  "license": "MIT"
}
gitpod /workspace/yarn-prebuild (main) $ yarn add gatsby-cli
yarn add v1.22.18
info No lockfile found.
[1/4] Resolving packages...
warning gatsby-cli > uuid@3.4.0: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
[2/4] Fetching packages...
[3/4] Linking dependencies...
[4/4] Building fresh packages...
success Saved lockfile.
warning Your current version of Yarn is out of date. The latest version is "1.22.19", while you're on "1.22.18".
info To upgrade, run the following command:
$ curl --compressed -o- -L https://yarnpkg.com/install.sh | bash
success Saved 266 new dependencies.
info Direct dependencies
└─ gatsby-cli@4.14.0
info All dependencies
├─ @ampproject/remapping@2.2.0
├─ @babel/compat-data@7.17.10
├─ @babel/core@7.18.0
├─ @babel/helper-annotate-as-pure@7.16.7
├─ @babel/helper-compilation-targets@7.17.10
├─ @babel/helper-create-class-features-plugin@7.18.0
├─ @babel/helper-hoist-variables@7.16.7
├─ @babel/helper-member-expression-to-functions@7.17.7
├─ @babel/helper-module-imports@7.16.7
├─ @babel/helper-module-transforms@7.18.0
├─ @babel/helper-replace-supers@7.16.7
├─ @babel/helper-simple-access@7.17.7
├─ @babel/helpers@7.18.0
├─ @babel/highlight@7.17.12
├─ @babel/plugin-syntax-typescript@7.17.12
├─ @babel/plugin-transform-typescript@7.18.1
├─ @babel/preset-typescript@7.17.12
├─ @babel/runtime@7.18.0
├─ @babel/traverse@7.18.0
├─ @hapi/topo@5.1.0
├─ @jridgewell/gen-mapping@0.3.1
├─ @jridgewell/resolve-uri@3.0.7
├─ @lmdb/lmdb-linux-x64@2.4.0
├─ @msgpackr-extract/msgpackr-extract-linux-x64@2.0.2
├─ @sideway/address@4.1.4
├─ @sideway/formula@3.0.0
├─ @sideway/pinpoint@2.0.0
├─ @sindresorhus/is@4.6.0
├─ @szmarczak/http-timer@4.0.6
├─ @turist/fetch@7.2.0
├─ @turist/time@0.0.2
├─ @types/cacheable-request@6.0.2
├─ @types/common-tags@1.8.1
├─ @types/http-cache-semantics@4.0.1
├─ @types/json-buffer@3.0.0
├─ @types/keyv@3.1.4
├─ @types/node-fetch@2.6.1
├─ @types/responselike@1.0.0
├─ @types/yoga-layout@1.9.2
├─ ansi-escapes@4.3.2
├─ ansi-regex@5.0.1
├─ arch@2.2.0
├─ async-retry-ng@2.0.1
├─ asynckit@0.4.0
├─ balanced-match@1.0.2
├─ better-opn@2.1.1
├─ boxen@5.1.2
├─ brace-expansion@1.1.11
├─ browserslist@4.20.3
├─ cacheable-lookup@5.0.4
├─ cacheable-request@7.0.2
├─ call-bind@1.0.2
├─ camelcase@5.3.1
├─ caniuse-lite@1.0.30001342
├─ chardet@0.7.0
├─ ci-info@2.0.0
├─ cli-boxes@2.2.1
├─ cli-cursor@3.1.0
├─ cli-width@3.0.0
├─ clipboardy@2.3.0
├─ cliui@6.0.0
├─ color-convert@2.0.1
├─ color-name@1.1.4
├─ combined-stream@1.0.8
├─ common-tags@1.8.2
├─ compress-brotli@1.3.8
├─ concat-map@0.0.1
├─ convert-hrtime@3.0.0
├─ convert-source-map@1.8.0
├─ create-gatsby@2.14.0
├─ cross-spawn@7.0.3
├─ crypto-random-string@2.0.0
├─ css-select@4.3.0
├─ css-what@6.1.0
├─ decode-uri-component@0.2.0
├─ decompress-response@6.0.0
├─ deep-extend@0.6.0
├─ defer-to-connect@2.0.1
├─ delayed-stream@1.0.0
├─ dom-converter@0.2.0
├─ dom-serializer@1.4.1
├─ domutils@2.8.0
├─ dot-prop@5.3.0
├─ duplexer3@0.1.4
├─ electron-to-chromium@1.4.137
├─ emoji-regex@8.0.0
├─ end-of-stream@1.4.4
├─ envinfo@7.8.1
├─ escalade@3.1.1
├─ escape-goat@2.1.1
├─ execa@5.1.1
├─ external-editor@3.1.0
├─ fastq@1.13.0
├─ figures@3.2.0
├─ file-type@16.5.3
├─ filter-obj@1.1.0
├─ find-up@4.1.0
├─ form-data@3.0.1
├─ fs-exists-cached@1.0.0
├─ fs.realpath@1.0.0
├─ gatsby-cli@4.14.0
├─ gatsby-telemetry@3.14.0
├─ gensync@1.0.0-beta.2
├─ get-caller-file@2.0.5
├─ get-stream@4.1.0
├─ git-up@4.0.5
├─ glob@7.2.3
├─ global-dirs@3.0.0
├─ globals@11.12.0
├─ got@11.8.3
├─ graceful-fs@4.2.10
├─ has-flag@4.0.0
├─ has-symbols@1.0.3
├─ has-yarn@2.1.0
├─ has@1.0.3
├─ hosted-git-info@3.0.8
├─ htmlparser2@6.1.0
├─ http2-wrapper@1.0.3
├─ human-signals@2.1.0
├─ iconv-lite@0.4.24
├─ ieee754@1.2.1
├─ import-from@4.0.0
├─ import-lazy@2.1.0
├─ imurmurhash@0.1.4
├─ inflight@1.0.6
├─ inherits@2.0.4
├─ ini@2.0.0
├─ inquirer@7.3.3
├─ is-extglob@1.0.0
├─ is-fullwidth-code-point@3.0.0
├─ is-glob@2.0.1
├─ is-installed-globally@0.4.0
├─ is-invalid-path@0.1.0
├─ is-npm@5.0.0
├─ is-obj@2.0.0
├─ is-path-inside@3.0.3
├─ is-stream@2.0.1
├─ is-valid-path@0.1.1
├─ is-yarn-global@0.3.0
├─ joi@17.6.0
├─ js-tokens@4.0.0
├─ jsesc@2.5.2
├─ json-buffer@3.0.1
├─ json5@2.2.1
├─ jsonfile@6.1.0
├─ keyv@4.2.9
├─ kleur@3.0.3
├─ latest-version@5.1.0
├─ lmdb@2.4.2
├─ locate-path@5.0.0
├─ lock@1.1.0
├─ lodash@4.17.21
├─ make-dir@3.1.0
├─ meant@1.0.3
├─ merge-stream@2.0.0
├─ mime-db@1.52.0
├─ mime-types@2.1.35
├─ mimic-fn@2.1.0
├─ minimatch@3.1.2
├─ minimist@1.2.6
├─ ms@2.1.2
├─ msgpackr-extract@2.0.2
├─ msgpackr@1.6.1
├─ mute-stream@0.0.8
├─ nice-try@1.0.5
├─ node-addon-api@4.3.0
├─ node-fetch@2.6.7
├─ node-gyp-build-optional-packages@5.0.2
├─ node-object-hash@2.3.10
├─ node-releases@2.0.4
├─ normalize-url@6.1.0
├─ npm-run-path@4.0.1
├─ nth-check@2.1.1
├─ object-inspect@1.12.1
├─ onetime@5.1.2
├─ open@7.4.2
├─ opentracing@0.14.7
├─ ordered-binary@1.2.5
├─ os-tmpdir@1.0.2
├─ p-cancelable@2.1.1
├─ p-finally@1.0.0
├─ p-limit@2.3.0
├─ p-locate@4.1.0
├─ p-try@2.2.0
├─ package-json@6.5.0
├─ parse-path@4.0.3
├─ parse-url@6.0.0
├─ path-exists@4.0.0
├─ path-is-absolute@1.0.1
├─ path-key@2.0.1
├─ peek-readable@4.1.0
├─ picocolors@1.0.0
├─ prepend-http@2.0.0
├─ pretty-error@2.1.2
├─ progress@2.0.3
├─ prompts@2.4.2
├─ proper-lockfile@4.1.2
├─ pupa@2.1.1
├─ qs@6.10.3
├─ query-string@6.14.1
├─ quick-lru@5.1.1
├─ read@1.0.7
├─ readable-stream@3.6.0
├─ readable-web-to-node-stream@3.0.2
├─ redux@4.1.2
├─ regenerator-runtime@0.13.9
├─ registry-auth-token@4.2.1
├─ registry-url@5.1.0
├─ renderkid@2.0.7
├─ require-directory@2.1.1
├─ require-main-filename@2.0.0
├─ resolve-alpn@1.2.1
├─ resolve-cwd@3.0.0
├─ restore-cursor@3.1.0
├─ retry@0.12.0
├─ reusify@1.0.4
├─ rimraf@3.0.2
├─ run-async@2.4.1
├─ rxjs@6.6.7
├─ safe-buffer@5.1.2
├─ safer-buffer@2.1.2
├─ semver-diff@3.1.1
├─ semver@6.3.0
├─ set-blocking@2.0.0
├─ shebang-command@2.0.0
├─ shebang-regex@3.0.0
├─ side-channel@1.0.4
├─ sisteransi@1.0.5
├─ source-map@0.7.3
├─ split-on-first@1.1.0
├─ stack-trace@0.0.10
├─ strict-uri-encode@2.0.0
├─ string_decoder@1.3.0
├─ strip-eof@1.0.0
├─ strip-final-newline@2.0.0
├─ strip-json-comments@2.0.1
├─ strtok3@6.3.0
├─ term-size@2.2.1
├─ through@2.3.8
├─ tmp@0.2.1
├─ to-fast-properties@2.0.0
├─ to-readable-stream@1.0.0
├─ token-types@4.2.0
├─ tr46@0.0.3
├─ tslib@1.14.1
├─ type-fest@0.20.2
├─ typedarray-to-buffer@3.1.5
├─ unique-string@2.0.0
├─ update-notifier@5.1.0
├─ url-parse-lax@3.0.0
├─ util-deprecate@1.0.2
├─ utila@0.4.0
├─ uuid@3.4.0
├─ weak-lru-cache@1.2.2
├─ webidl-conversions@3.0.1
├─ whatwg-url@5.0.0
├─ which-module@2.0.0
├─ which@2.0.2
├─ wrap-ansi@7.0.0
├─ write-file-atomic@3.0.3
├─ y18n@4.0.3
├─ yallist@4.0.0
├─ yargs-parser@18.1.3
├─ yargs@15.4.1
├─ yoga-layout-prebuilt@1.10.0
└─ yurnalist@2.1.0
Done in 32.10s.
gitpod /workspace/yarn-prebuild (main) $ cat package.json
{
  "name": "yarn-prebuild",
  "version": "1.0.0",
  "main": "index.js",
  "repository": "https://github.com/jldec/yarn-prebuild.git",
  "author": "Jurgen Leschner <jldec@ciaosoft.com>",
  "license": "MIT",
  "dependencies": {
    "gatsby-cli": "^4.14.0"
  }
}
gitpod /workspace/yarn-prebuild (main) $ gp init

# [edited .gitpod.yml...]

gitpod /workspace/yarn-prebuild (main) $ yarn gatsby -h
yarn run v1.22.18
$ /workspace/yarn-prebuild/node_modules/.bin/gatsby -h
╔════════════════════════════════════════════════════════════════════════╗
║                                                                        ║
║   Gatsby collects anonymous usage analytics                            ║
║   to help improve Gatsby for all users.                                ║
║                                                                        ║
║   If you'd like to opt-out, you can use `gatsby telemetry --disable`   ║
║   To learn more, checkout https://gatsby.dev/telemetry                 ║
║                                                                        ║
╚════════════════════════════════════════════════════════════════════════╝
Usage: gatsby <command> [options]

Commands:
  gatsby develop                      Start development server. Watches files, rebuilds, and hot reloads if something changes
  gatsby build                        Build a Gatsby project.
  gatsby serve                        Serve previously built Gatsby site.
  gatsby info                         Get environment information for debugging and issue reporting
  gatsby clean                        Wipe the local gatsby environment including built assets and cache
  gatsby repl                         Get a node repl with context of Gatsby environment, see (https://www.gatsbyjs.com/docs/gatsby-repl/)
  gatsby plugin <cmd> [plugins...]    Useful commands relating to Gatsby plugins
  gatsby new [rootPath] [starter]     Create new Gatsby project.
  gatsby telemetry                    Enable or disable Gatsby anonymous analytics collection.
  gatsby options [cmd] [key] [value]  View or set your gatsby-cli configuration settings.

Options:
  --verbose                Turn on verbose output                                                                                                 [boolean] [default: false]
  --no-color, --no-colors  Turn off the color in output                                                                                           [boolean] [default: false]
  --json                   Turn on the JSON logger                                                                                                [boolean] [default: false]
  -h, --help               Show help                                                                                                                               [boolean]
  -v, --version            Show the version of the Gatsby CLI and the Gatsby package in the current project                                                        [boolean]

Done in 1.32s.
gitpod /workspace/yarn-prebuild (main) $ ^C
gitpod /workspace/yarn-prebuild (main) $ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitpod.yml
        node_modules/
        package.json
        yarn.lock

nothing added to commit but untracked files present (use "git add" to track)
gitpod /workspace/yarn-prebuild (main) $ echo node_modules>.gitignore
gitpod /workspace/yarn-prebuild (main) $ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        .gitpod.yml
        package.json
        yarn.lock

nothing added to commit but untracked files present (use "git add" to track)
gitpod /workspace/yarn-prebuild (main) $ 
```
