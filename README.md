# okaru-view

**English** · [Español](#español)

The image viewer of [OKARU](https://github.com/MrAndyVF/okaru) (郁): photos (including RAW), animations and metadata, with the shell's look and theme.

## Install

It ships in OKARU's pacman repository `[okaru]` (set up by OKARU's installer):

```sh
sudo pacman -S okaru-view
```

## Build

It builds against OKARU's shared core, provided by the `okaru-core` package:

```sh
meson setup build && meson compile -C build
meson test -C build
# Run it with the translations from this repository:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-view
```

Translations live in `apps/viewer/translations/` (English and Spanish).

## License

MIT.

---

## Español

El visor de imágenes de [OKARU](https://github.com/MrAndyVF/okaru) (郁): fotos (también RAW), animaciones y metadatos, con el aspecto y el tema de la shell.

### Instalar

Viene en el repositorio pacman de OKARU, `[okaru]` (lo configura el instalador de OKARU):

```sh
sudo pacman -S okaru-view
```

### Compilar

Se compila contra el núcleo compartido de OKARU, que trae el paquete `okaru-core`:

```sh
meson setup build && meson compile -C build
meson test -C build
# Ejecutarla con las traducciones de este repositorio:
OKARU_APPS_DIR=$PWD/apps ./build/okaru-view
```

Las traducciones están en `apps/viewer/translations/` (inglés y español).

### Licencia

MIT.
