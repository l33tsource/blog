---
description: Enable nice splash screen
published: true
categories: [blog]
tags: [Fedora, splash screen]
layout: post
---

Just edit in `/etc/default/grub` the GRUB_CMDLINE_LINUX parameter and remove rhgb quiet.

>GRUB\_CMDLINE\_LINUX="vconsole.font=latarcyrheb-sun16 rd.luks.uuid=luks-3edcc7bd-3881-45e9-9a03-26e32fd6e14e $([ -x /usr/sbin/rhcrashkernel-param ] && /usr/sbin/rhcrashkernel-param || :) rhgb quiet"

After that you need to rebuild your grub with something like this:

>grub2-mkconfig -o /boot/grub2/grub.cfg

And now you have a fancy splash screen with text output. 