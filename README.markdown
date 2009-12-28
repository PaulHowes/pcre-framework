# INTRODUCTION

PCRE is an incredibly useful regular-expression engine library that works on
virtually every major operating system.  One can think of PCRE (or any library
for that matter) as coming in two flavors:  An SDK that includes the headers
and library that a developer would use, and the runtime version that only
includes the library.  Apple makes this easy with its support for frameworks.

# IMPLEMENTATION

This framework consists of several components:

1.  PCRE source code from http://pcre.org/

    Unfortunately this is a pure snapshot and not a submodule.  The author of
    PCRE does not appear to allow public read access to his subversion
    repository which will complicate future updates.  As of this writing,
    PCRE 8.0 is the current snapshot.

2.  AGRegex source code from http://github.com/mdiep/AGRegex/

    This is used as a submodule and can be updated as such.  AGRegex internally
    depends on a very old version (6.7) of PCRE.  There are only two files of
    interest in this project, but it's easier to grab everything.

# DOWNLOADING

Clone the repository with
`git clone git://github.com/pahowes/pcre-framework.git`

# COMPILING

Open `pcre.xcodeproj` with XCode 3.2 or later, or use `xcodebuild` to build it
from the command line.

Under the `build` directory you will find either a debug or a release version
of the framework, depending on the type of compile.  The base library path
embedded into the binary is `@loader_path/../Frameworks` which should be
sufficient to include the framework with your own application or plug-in
bundle.
