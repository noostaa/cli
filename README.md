# Noostaa Agent CLI

Command-line access to Noostaa workouts for assistants and terminal users.
This public distribution repository contains compiled binaries; the CLI source
is maintained separately.

## Download

Get the archive for your operating system and architecture from the
[latest release](https://github.com/noostaa/cli/releases/latest):

- Apple Silicon Mac: `noostaa-agent_*_darwin_arm64.zip`
- Intel Mac: `noostaa-agent_*_darwin_amd64.zip`
- Linux ARM64: `noostaa-agent_*_linux_arm64.tar.gz`
- Linux x86_64: `noostaa-agent_*_linux_amd64.tar.gz`
- Windows x86_64: `noostaa-agent_*_windows_amd64.zip`
- Windows ARM64: `noostaa-agent_*_windows_arm64.zip`

Extract the archive and move `noostaa-agent` (or `noostaa-agent.exe` on Windows)
to a directory on your `PATH`.

On macOS or Linux, for example:

```sh
mkdir -p "$HOME/.local/bin"
# Run from the extracted directory containing noostaa-agent:
install -m 755 noostaa-agent "$HOME/.local/bin/noostaa-agent"
export PATH="$HOME/.local/bin:$PATH"
noostaa-agent version
```

Add `$HOME/.local/bin` to your shell's PATH configuration to keep it available
in new terminal sessions.

## macOS signing status

The initial v0.1.0 release is unsigned and is not Apple-notarized.
Use v0.1.1 or newer for notarized macOS builds.

Starting with v0.1.1, macOS releases are Developer ID signed and Apple-notarized.
Choose the `.pkg` installer for Apple Silicon or Intel to install
`noostaa-agent` into `/usr/local/bin`, or download the corresponding ZIP.

## Verify downloads

Each release includes `checksums.txt` containing SHA-256 checksums. Download it
alongside your archive, then compare the matching checksum:

```sh
# Replace ARCHIVE with your downloaded archive's filename:
shasum -a 256 ARCHIVE
# Linux alternative:
sha256sum ARCHIVE
# Windows PowerShell:
Get-FileHash .\ARCHIVE -Algorithm SHA256
```

## Connect to Noostaa

```sh
noostaa-agent version
noostaa-agent login
noostaa-agent status
noostaa-agent workout list
```

Login opens your browser to authorize access to your Noostaa account. The
default service is `https://app.noostaa.com`.

Learn more at [noostaa.com](https://noostaa.com).
