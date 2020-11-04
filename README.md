# Elkowar's Phocus-Phork
This GTK3 theme is a phork of phisch's phocus theme, adjusted to match the gruvbox colorscheme.

## Installation

### Nix

```nix
gtk = {
  enable = true;
  theme = let
      phocus = pkgs.stdenv.mkDerivation {
        name = "elkowars_phocus";
        src = builtins.fetchTarball https://github.com/elkowar/gtk/archive/master.tar.gz;
        nativeBuildInputs = [ pkgs.sass ];
        installFlags = [ "DESTDIR=$(out)" "PREFIX=" ];
      };
    in {
    package = phocus;
    name = "elkowars_phocus";
  };
};
```
### From source

install `sass`,
then just run `make && sudo make install` to build and install the theme.
