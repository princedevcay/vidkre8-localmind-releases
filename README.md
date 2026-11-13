# VidKre8 LocalMind: model list and engine builds

VidKre8 LocalMind is a Mac and Windows app by PrinceCaleb.dev that checks a computer, picks offline AI tools that fit it, and sets them up. This repository holds the small public files the app reads. It holds no source code and no installers.

## What is here

| Path | What it is |
|---|---|
| `staging/catalog.json` | The model list for test builds: which AI tools the app can offer, where each file is published, and its SHA-256 fingerprint |
| `staging/catalog.sig` | The Ed25519 signature over the exact bytes of that list. The app uses the list only if this signature matches a key built into the app |
| `staging/version.json` | The newest app version number, so the app can say an update is ready |
| Releases | Builds of the open-source programs that run the AI tools, for computers the original projects publish no build for |

`staging` is for invited testers and is signed with a test key. Public builds will use a separate list signed with a production key.

## Engine builds

The builds under Releases are unmodified builds of these projects, with their licence files inside each archive:

| Program | Project | Licence | Source version |
|---|---|---|---|
| whisper.cpp (speech to text) | github.com/ggml-org/whisper.cpp | MIT | tag b5454 (v1.9.5), commit d1be6fde11ac6e0407606b4e42fe72d34add8037 |
| stable-diffusion.cpp (pictures), Intel Mac, processor only | github.com/leejet/stable-diffusion.cpp | MIT | master-1092-5d78740, commit 5d787408c0e053568c4558e3c9043e8ebabd4cae |

The app downloads a build only when a signed model list names it, and installs it only if its SHA-256 matches the list.

## Model files

Model files are not stored here. The list points to each publisher's own repository on Hugging Face, pinned to an exact version.

## Contact

Prince Caleb, princecaleb.dev. To report a security problem, see [SECURITY.md](SECURITY.md).
