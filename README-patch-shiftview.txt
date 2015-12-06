Source     : http://lists.suckless.org/dev/att-7590/shiftview.c
dwm Version: 6.1
URL        : http://lists.suckless.org/dev/1104/7590.html

Info       :
-----------------------------------------------------------------------------------------------------------------
 From: Fernando C.V. <ferkiwi_AT_gmail.com>
Date: Tue, 19 Apr 2011 20:32:35 +0200

Hi,

I've got what I think might be a better implementation of the
nextprevtag.c patch.

It's just a simple bitwise left/right circular shift of the tagset,
avoiding the loop that the older patch used and with the additional
benefit of working also for switching tagset with multiple tags
selected.

I did it before realizing there was already a "nextprevtag.c", and
although it's very simple, since it's a bit different in functionality
I thought that maybe it would be useful for someone else.

--
Fernando Carmona Varo


