# PyDevices PyScript template

A minimal, installable PyScript application for the portable
[PyDevices](https://github.com/PyDevices/pydevices) display stack.

Use this repository as a GitHub template, edit `main.py`, and enable GitHub
Pages with **GitHub Actions** as the source. The included workflow deploys the
app, and the service worker caches both the application shell and the pinned
PyScript runtime for offline launches after the first successful visit.
The template also pins PyDevices source files to release `v0.0.17`, so a new
app does not silently change when the product's default branch advances.

## Customize

- Edit `main.py` for application behavior.
- Edit `pyscript.json` to add PyDevices source files or Pyodide packages.
- Change the app name, colors, and icons in `index.html`, `manifest.json`, and
  `style.css`.
- Change `PYSCRIPT_VERSION` in `scripts/vendor_pyscript.sh` when you choose to
  update the browser runtime.

## Preview locally

```bash
./scripts/vendor_pyscript.sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>. Do not open `index.html` directly from the
filesystem; PyScript and service workers require an HTTP origin.

## Verify

```bash
python3 -m unittest discover -s tests -v
```

The template uses the `py` runtime (Pyodide) for the broadest pip-wheel path.
The same PyDevices source packages remain portable to MicroPython and
CircuitPython; see [pydevices-examples](https://github.com/PyDevices/pydevices-examples)
for complete cross-runtime applications and the full gallery.

MIT licensed. See `LICENSE`.
