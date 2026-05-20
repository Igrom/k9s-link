# k9s-link

Creates a "link" to your current k9s view and, by default, copies it to your clipboard.

## Installation

### Mac

```bash
curl https://raw.githubusercontent.com/Igrom/k9s-link/refs/heads/master/k9s-link.yaml -o "$HOME/Library/Application Support/k9s/plugins/k9s-link.yaml"
```

### Manual

Download the `k9s-link.yaml` file and place it in your k9s plugin directory. See https://k9scli.io/topics/plugins/ for a list of default plugin directories.

## How to use 
Press `Shift-Y` while viewing a resource in k9s to copy a link.

Example interaction:

```bash
# after pressing the keybinding in k9s
CONTEXT=docker-rancher
NAMESPACE=website
RESOURCE_KIND=pods
RESOURCE_NAME=website-67d9876ffc-7zjlw

k9s link:
        k9s --context docker-rancher -n website --command "pods /website-67d9876ffc-7zjlw"
```

Running the command in your terminal should reproduce the view (except for containers: in that case, the view is scoped to the pod).

## Configuration
### K9S_LINK_COPY_TO_CLIPBOARD: disabling copy-to-clipboard
You can disable automatic copying to clipboard (useful if you're not using a clipboard manager) by setting the environment variable `K9S_LINK_COPY_TO_CLIPBOARD` to `false`.

## License
GPL-3.0
