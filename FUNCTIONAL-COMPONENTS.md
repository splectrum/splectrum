# SPlectrum Functional Components

*What SPlectrum can demonstrate and deliver as functional capabilities*

## Status Legend
- ✅ **Complete**: Fully implemented and operational
- 🔧 **Partial**: Working but needs enhancement/completion
- ❌ **Missing**: Required but not yet implemented
- 🗺️ **Roadmap**: Planned but not MVP required

| Organization | Component | Status | Notes |
|--------------|-----------|--------|-------|
| **carambah** |  |  |  |
| | spl-dev | 🔧 Partial | Development instance currently in use but not complete yet |
| | spl-claude-swift | ❌ Missing | SPL install deployed with claude-swift repo for common tasks and standardised Claude tool access |
| **infometish** |  |  |  |
| | container wrapper | ❌ Missing | Container orchestration and deployment wrapper |
| | install wrapper | ❌ Missing | Installation and setup wrapper |
| **sesameh** |  |  |  |
| | [claude-swift](https://github.com/sesameh/claude-swift) | 🔧 Partial | The current standard SPL AI shared workflow repository |
| **splectrum** |  |  |  |
| | cs | ❌ Missing | claude-swift app API package, core of spl-claude-swift install |
| | cs/git | ❌ Missing | The claude swift git API |
| | cs/issue | ❌ Missing | Issue handling through SPlectrum DSL |
| | gp | 🔧 Partial | A general purpose module package |
| | gp/config | 🔧 Partial | A general purpose app configuration API |
| | gp/fs | 🔧 Partial | A general purpose filesystem API |
| | gp/test | 🔧 Partial | Uses functional execution audit for testing, includes coding standards and functional testing |
| | spl/app/create | ✅ Complete | Command to create an action from a batch of commands to be ported to spl/action API |
| | spl/app/help | 🔧 Partial | Currently generates item help only, needs to move to its own API spl/help, also needs AVRO integration |
| | spl/app/process | ✅ Complete | Command parsing method to be ported to spl/command API |
| | spl | 🔧 Partial | The core APIs of SPlectrum |
| | spl/app/wrap | ✅ Complete | Command to wrap a bash or python script into an action to be ported to spl/wrap API |
| | spl/avro | ❌ Missing | The API for the essential AVRO functionality (not yet figured out exactly what this will look like) |
| | spl/blob | ✅ Complete | Binary data layer API |
| | spl/console | ✅ Complete | Console API |
| | spl/data | ✅ Complete | Streaming data layer API |
| | spl/error | 🔧 Partial | Execution pipeline error API |
| | spl/exec | 🔧 Partial | The execution pipeline API |
| | spl/package | ✅ Complete | Package management API |
| | spl/rpc | ❌ Missing | The API for the AVRO RPC functionality |
| | spl/void | 🔧 Partial | Miscellaneous API |
| | tools | 🔧 Partial | A module package of API wrappers around core tools |
| | tools/7zip | ✅ Complete | Wrapper API around 7zip |
| | tools/git | 🔧 Partial | Git operations via SPL APIs instead of external tools |

