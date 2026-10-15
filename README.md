# ZapConvert Unraid templates

Community Applications templates for [ZapConvert](https://github.com/zapconvert/zapconvert), a
private file converter (PDF, Office, images, spreadsheets, audio and video).

ZapConvert runs as three containers on one custom Docker network:

| Template | Image | Role |
| --- | --- | --- |
| `zapconvert-gotenberg.xml` | `gotenberg/gotenberg:8` | Office documents to PDF |
| `zapconvert-media-worker.xml` | `ghcr.io/zapconvert/zapconvert-media-worker` | Audio, video, PDF to Word and Excel |
| `zapconvert.xml` | `ghcr.io/zapconvert/zapconvert` | Web interface (port 3000) |

1. In the Unraid terminal, once: `docker network create zapconvert`
2. Install `zapconvert-gotenberg` and `zapconvert-media-worker` on that network.
3. Install `zapconvert` on the same network.

The two companion containers publish no ports. Only `zapconvert` can reach them.

Support: [GitHub issues](https://github.com/zapconvert/zapconvert/issues).
