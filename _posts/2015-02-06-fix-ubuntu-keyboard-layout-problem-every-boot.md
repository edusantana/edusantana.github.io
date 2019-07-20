---
layout: post
title: "Fix ubuntu keyboard layout problem every boot"
description: ""
category: "linux"
tags: ["linux","keyboard"]
---
{% include JB/setup %}

This post fix the ubuntu keyboard layout problem after every reboot.

Open an terminal and type:

    dconf dump /desktop/ibus/general/

It will output:

    [/]
    engines-order=['xkb:us::eng', 'xkb:br::por', 'xkb:us::eng']
    preload-engine-mode=1
    use-system-keyboard-layout=false
    preload-engines=['xkb:br::por', 'xkb:us::eng', 'xkb:br:nodeadkeys:por']
    preload-engines-inited=true
    version='1.5.5'

You will need to change `use-system-keyboard-layout` to `true`, run:

    dconf write /desktop/ibus/general/use-system-keyboard-layout true

To see changes, run the first command again:

    ~$ dconf dump /desktop/ibus/general/
    [/]
    engines-order=['xkb:us::eng', 'xkb:br::por', 'xkb:us::eng']
    preload-engine-mode=1
    use-system-keyboard-layout=true
    preload-engines=['xkb:br::por', 'xkb:us::eng', 'xkb:br:nodeadkeys:por']
    preload-engines-inited=true
    version='1.5.5'

You can see that it has chaged. Just reboot, and that's all!

