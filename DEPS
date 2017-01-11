# This file is automatically processed to create .DEPS.git which is the file
# that gclient uses under git.
#
# See http://code.google.com/p/chromium/wiki/UsingGit
#
# To test manually, run:
#   python tools/deps2git/deps2git.py -o .DEPS.git -w <gclientdir>
# where <gcliendir> is the absolute path to the directory containing the
# .gclient file (the parent of 'src').
#
# Then commit .DEPS.git locally (gclient doesn't like dirty trees) and run
#   gclient sync
# Verify the thing happened you wanted. Then revert your .DEPS.git change
# DO NOT CHECK IN CHANGES TO .DEPS.git upstream. It will be automatically
# updated by a bot when you modify this one.
#
# When adding a new dependency, please update the top-level .gitignore file
# to list the dependency's destination directory.

vars = {
  'chromium_git': 'https://chromium.googlesource.com',
  'fuchsia_git': 'https://fuchsia.googlesource.com',
  'skia_git': 'https://skia.googlesource.com',
  'github_git': 'https://github.com',
  'base_revision': 'b2412302ed4e45bfb47d7b5c0c3418077009e1ce',
  'skia_revision': '130a118cc68f8f9973e9572356011de378463fea',

    # Necessary for some packages we rely on for generating the patched sdk.
   "dart_root" : "src/dart",
   "github_mirror":
       "https://chromium.googlesource.com/external/github.com/dart-lang/%s.git",
   "github_dartlang": "https://github.com/dart-lang/%s.git",
   "args_tag": "@0.13.5",
   "async_tag": "@1.11.1",
   "charcode_tag": "@1.1.0",
   "collection_tag": "@1.9.1",
   "convert_tag": "@2.0.1",
   "crypto_tag" : "@2.0.1",
   "csslib_tag" : "@0.13.2",
   "glob_tag": "@1.1.3",
   "html_tag" : "@0.13.0",
   "isolate_tag": "@0.2.3",
   "logging_tag": "@0.11.3+1",
   "package_config_tag": "@1.0.0",
   "path_tag": "@1.3.9",
   "plugin_tag": "@0.2.0",
   "source_span_tag": "@1.2.3",
   "string_scanner_tag": "@1.0.0",
   "typed_data_tag": "@1.1.3",
   "utf_tag": "@0.9.0+3",
   "watcher_tag": "@0.9.7+3",
   "yaml_tag": "@2.1.10",


  # Note: When updating the Dart revision, ensure that all entries that are
  # dependencies of dart are also updated
  'dart_revision': 'origin/master',
  'dart_boringssl_gen_revision': '62c20247d582444cb2804f9ea4e3abaa6e47f6a5',
  'dart_boringssl_revision': '8d343b44bbab829d1a28fdef650ca95f7db4412e',
  'dart_observatory_packages_revision': '26aad88f1c1915d39bbcbff3cad589e2402fdcf1',
  'dart_root_certificates_revision': 'aed07942ce98507d2be28cbd29e879525410c7fc',

  'buildtools_revision': '1f4c1c3bd3bd4c991e6565a0dc509c8d8a3f90b4',
}

# Only these hosts are allowed for dependencies in this DEPS file.
# If you need to add a new host, contact chrome infrastructure team.
allowed_hosts = [
  'chromium.googlesource.com',
  'fuchsia.googlesource.com',
  'github.com',
  'skia.googlesource.com',
]

deps = {
  'src': 'https://github.com/flutter/buildroot.git' + '@' + '8bdd40871339d8297b2681bbe218543d80ceda1b',

   # Fuchsia compatibility
   #
   # The dependencies in this section should match the layout in the Fuchsia gn
   # build. Eventually, we'll manage these dependencies together with Fuchsia
   # and not have to specific specific hashes.

  'src/lib/ftl':
   Var('fuchsia_git') + '/ftl' + '@' + '9f51f24056554352b045fda338e9101c0e5af272',

  'src/lib/tonic':
   Var('fuchsia_git') + '/tonic' + '@' + '4214b35e02a1286a5fb98895d0c480fa0da10f6d',

  'src/lib/zip':
   Var('fuchsia_git') + '/zip' + '@' + '92dc87ca645fe8e9f5151ef6dac86d8311a7222f',

  'src/third_party/gtest':
   Var('fuchsia_git') + '/third_party/gtest' + '@' + 'c00f82917331efbbd27124b537e4ccc915a02b72',

  'src/third_party/rapidjson':
   Var('fuchsia_git') + '/third_party/rapidjson' + '@' + '9defbb0209a534ffeb3a2b79d5ee440a77407292',

   # Chromium-style
   #
   # As part of integrating with Fuchsia, we should eventually remove all these
   # Chromium-style dependencies.

  'src/base':
   Var('github_git') + '/flutter/base.git' + '@' +  Var('base_revision'),

  'src/buildtools':
   Var('fuchsia_git') + '/buildtools' + '@' +  Var('buildtools_revision'),

  # TODO(abarth): Remove in favor of //third_party/gtest
  'src/testing/gtest':
   Var('chromium_git') + '/external/googletest.git' + '@' + '23574bf2333f834ff665f894c97bef8a5b33a0a9',

  'src/testing/gmock':
   Var('chromium_git') + '/external/googlemock.git' + '@' + '29763965ab52f24565299976b936d1265cb6a271',

  'src/third_party/icu':
   Var('chromium_git') + '/chromium/deps/icu.git' + '@' + 'c3f79166089e5360c09e3053fce50e6e296c3204',

  'src/dart':
    Var('chromium_git') + '/external/github.com/dart-lang/sdk.git' + '@' + Var('dart_revision'),

  'src/third_party/boringssl':
    Var('github_git') + '/dart-lang/boringssl_gen.git' + '@' + Var('dart_boringssl_gen_revision'),

  'src/third_party/boringssl/src':
   'https://boringssl.googlesource.com/boringssl.git' + '@' + Var('dart_boringssl_revision'),

  'src/dart/third_party/observatory_pub_packages':
   Var('chromium_git') +
   '/external/github.com/dart-lang/observatory_pub_packages' + '@' +
   Var('dart_observatory_packages_revision'),


   Var("dart_root") + "/third_party/pkg/path":
       (Var("github_mirror") % "path") + Var("path_tag"),
   Var("dart_root") + "/third_party/pkg/html":
       (Var("github_mirror") % "html") + Var("html_tag"),
   Var("dart_root") + "/third_party/pkg/plugin":
       (Var("github_mirror") % "plugin") + Var("plugin_tag"),
   Var("dart_root") + "/third_party/pkg_tested/package_config":
       (Var("github_mirror") % "package_config") +
       Var("package_config_tag"),
   Var("dart_root") + "/third_party/pkg/charcode":
       (Var("github_mirror") % "charcode") + Var("charcode_tag"),
   Var("dart_root") + "/third_party/pkg/source_span":
       (Var("github_mirror") % "source_span") + Var("source_span_tag"),
   Var("dart_root") + "/third_party/pkg/watcher":
       (Var("github_mirror") % "watcher") + Var("watcher_tag"),
   Var("dart_root") + "/third_party/pkg/isolate":
       (Var("github_dartlang") % "isolate") + Var("isolate_tag"),
   Var("dart_root") + "/third_party/pkg/yaml":
       (Var("github_mirror") % "yaml") + Var("yaml_tag"),
   Var("dart_root") + "/third_party/pkg/args":
       (Var("github_mirror") % "args") + Var("args_tag"),
   Var("dart_root") + "/third_party/pkg/csslib":
       (Var("github_mirror") % "csslib") + Var("csslib_tag"),
   Var("dart_root") + "/third_party/pkg/async":
       (Var("github_mirror") % "async") + Var("async_tag"),
   Var("dart_root") + "/third_party/pkg/convert":
       "https://github.com/dart-lang/convert.git" + Var("convert_tag"),
   Var("dart_root") + "/third_party/pkg/crypto":
       (Var("github_mirror") % "crypto") + Var("crypto_tag"),
   Var("dart_root") + "/third_party/pkg/glob":
       (Var("github_mirror") % "glob") + Var("glob_tag"),
   Var("dart_root") + "/third_party/pkg/logging":
       (Var("github_mirror") % "logging") + Var("logging_tag"),
   Var("dart_root") + "/third_party/pkg/typed_data":
       (Var("github_dartlang") % "typed_data") + Var("typed_data_tag"),
   Var("dart_root") + "/third_party/pkg/utf":
       (Var("github_mirror") % "utf") + Var("utf_tag"),
   Var("dart_root") + "/third_party/pkg/collection":
       (Var("github_mirror") % "collection") + Var("collection_tag"),
   Var("dart_root") + "/third_party/pkg/string_scanner":
       (Var("github_mirror") % "string_scanner") +
       Var("string_scanner_tag"),

  'src/third_party/root_certificates':
   Var('chromium_git') +
   '/external/github.com/dart-lang/root_certificates' + '@' +
   Var('dart_root_certificates_revision'),

  'src/third_party/skia':
   Var('skia_git') + '/skia.git' + '@' +  Var('skia_revision'),

  'src/third_party/yasm/source/patched-yasm':
   Var('chromium_git') + '/chromium/deps/yasm/patched-yasm.git' + '@' + '4671120cd8558ce62ee8672ebf3eb6f5216f909b',

  'src/third_party/libjpeg-turbo':
   Var('skia_git') + '/third_party/libjpeg-turbo.git' + '@' + 'debddedc75850bcdeb8a57258572f48b802a4bb3',

   # Headers for Vulkan 1.0
   'src/third_party/vulkan':
   Var('github_git') + '/KhronosGroup/Vulkan-Docs.git' + '@' + 'e29c2489e238509c41aeb8c7bce9d669a496344b',
}

recursedeps = [
  'src/buildtools',
]

deps_os = {
  'android': {
    'src/third_party/colorama/src':
     Var('chromium_git') + '/external/colorama.git' + '@' + '799604a1041e9b3bc5d2789ecbd7e8db2e18e6b8',

    'src/third_party/jsr-305/src':
        Var('chromium_git') + '/external/jsr-305.git' + '@' + '642c508235471f7220af6d5df2d3210e3bfc0919',

    'src/third_party/junit/src':
      Var('chromium_git') + '/external/junit.git' + '@' + '45a44647e7306262162e1346b750c3209019f2e1',

    'src/third_party/mockito/src':
      Var('chromium_git') + '/external/mockito/mockito.git' + '@' + 'ed99a52e94a84bd7c467f2443b475a22fcc6ba8e',

    'src/third_party/robolectric/lib':
      Var('chromium_git') + '/chromium/third_party/robolectric.git' + '@' + '6b63c99a8b6967acdb42cbed0adb067c80efc810',

    'src/third_party/freetype2':
       Var('fuchsia_git') + '/third_party/freetype2' + '@' + 'e23a030e9b43c648249477fdf7bf5305d2cc8f59',
  },
}


hooks = [
  {
    # This clobbers when necessary (based on get_landmines.py). It must be the
    # first hook so that other things that get/generate into the output
    # directory will not subsequently be clobbered.
    'name': 'landmines',
    'pattern': '.',
    'action': [
        'python',
        'src/build/landmines.py',
    ],
  },
  {
    'name': 'download_android_tools',
    'pattern': '.',
    'action': [
        'python',
        'src/tools/android/download_android_tools.py',
    ],
  },
  {
    'name': 'clang',
    'pattern': '.',
    'action': ['/bin/bash', 'src/buildtools/update.sh', '--toolchain', '--ninja', '--gn'],
  },
  {
    # Pull dart sdk if needed
    'name': 'dart',
    'pattern': '.',
    'action': ['python', 'src/tools/dart/update.py'],
  },
  {
    # Ensure that we don't accidentally reference any .pyc files whose
    # corresponding .py files have already been deleted.
    'name': 'remove_stale_pyc_files',
    'pattern': 'src/tools/.*\\.py',
    'action': [
        'python',
        'src/tools/remove_stale_pyc_files.py',
        'src/tools',
    ],
  },
  {
    "name": "checked_in_dart_sdks",
    "pattern": ".",
    "action": [
      "download_from_google_storage",
      "--no_auth",
      "--no_resume",
      "--bucket",
      "dart-dependencies",
      "--recursive",
      "--auto_platform",
      "--extract",
      "--directory",
      "src/dart/tools/sdks",
    ],
  },
]
