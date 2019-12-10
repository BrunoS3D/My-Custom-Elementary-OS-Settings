# My-Custom-Elementary-OS-Settings

### explorador de arquivos, abrir arquivos com duplo click
```console
$ gsettings set io.elementary.files.preferences single-click false
```

### layout
```console
gsettings set org.gnome.desktop.interface gtk-theme 'elementary'
gsettings set org.pantheon.desktop.gala.appearance button-layout 'close,maximize,minimize'
```

### dark theme
```console
sudo apt-get install --yes software-properties-common && sudo apt-add-repository --yes ppa:philip.scott/elementary-tweaks && sudo apt-get install --yes elementary-tweak
gsettings set io.elementary.terminal.settings prefer-dark-style true
```

### inicializar sistema com digital vibrance aplicado

editar/criar o arquivo a seguir:
> ~/.nvidia-settings-rc

alterar os campos a seguir:

```cfg
# tela principal
NOMEDOPC:0[DPY:HDMI-0]/DigitalVibrance=500
# tela secundaria
NOMEDOPC:0[DPY:DP-2]/DigitalVibrance=500
```
editar/criar o arquivo a seguir:
> ~/.xinitrc

inserir os commandos a seguir:

```console
nvidia-settings --load-config-only &
. /etc/X11/xinit/xinitrc
```
