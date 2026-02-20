---
layout: post
title: "Did you know about EA’s Open Source software?"
date: "2014-06-25 12:30:25 -0700"
permalink: /2014/06/25/ea-open-source-software/
categories:
  - "Uncategorized"
---

**UPDATE - See [CORRECTION – EA’s Free/Libre Software](<https://bobsummerwill.wordpress.com/2014/06/28/correction-eas-freelibre-software/>).**

Do you know that EA releases various of its foundational technologies as part of its LGPL compliance obligations? EA should be talking about this much more, because these technologies are great! They have had years and years of love poured into them, and have been used to ship numerous AAA titles across mutliple hardware platforms.

And you can use them too. You just didn't know.

They are currently being released as ZIP files to <http://gpl.ea.com>. It would be way better if there was just an EA public Github account. Maybe some day?

EAWebKit is the conduit through which most of the technologies get released. EAWebKit is the public WebKit technology, re-vectored on top of EA base technology. It builds as a self-contained DLL, to isolate the LGPL-ness.

If you download one of the ZIPs, and go into the **EAWebKitSupportPackages** folder, you will find the "goodies". They have been stripped of all of their source build system files and documentation, but all the source code and headers are there, along with generated Visual Studio SLN/VCPROJX files.

     * coreallocator - memory allocator interface
     * DirtySDK - sockets library
     * EAAssert - assertion handling
     * EABase - base types and #defines
     * EAIO - I/O library
     * EASTL - game-friendly STL implementation (described [in public by Paul Pedriana in 2007](<http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2271.html>))
     * EAText - Text-rendering library (sitting on top of FreeType)
     * EAWebkit - Fork of the Webkit project, ported on top of EA base technology
     * PPMalloc - Superb memory management tech from Paul Pedriana
     * UTFXml - XML library

You will also see the following non-EA packages which EAWebkit also depends on. These versions may just be vanilla releases or may have EA-specific additional edits. I've not checked:

     * cairo - 2D graphics library, see <http://cairographics.org/>
     * FreeType - Font-rendering library, see <http://www.freetype.org/>
     * JavaScriptCore - The built-in JS engine for Webkit (AKA SquirrelFish or Nitro), see <http://trac.webkit.org/wiki/JavaScriptCore>
     * libjpeg - library for reading and writing JPEG image files, see <http://libjpeg.sourceforge.net/>
     * libpng - library for reading and writing PNG image files, see <http://www.libpng.org/pub/png/libpng.html>
     * pixman - low-level library for pixel manipulation, see <http://www.pixman.org/>
     * SQLite - self-contained SQL database library, see <http://www.sqlite.org/>
     * zlib - compression library, see <http://www.zlib.net/>

UPDATE:

<https://twitter.com/m18e/status/481899786258219008>

If you download [EAWebKit-13.3.2.0.0](<http://gpl.ea.com/packages/EAWebKit_13.3.2.0.0.zip>), that version contains SLNs for Win32 and Win64, in addition to PS4 and XBOX One.

The newer [EAWebKit-13.4.1.0.0](<http://gpl.ea.com/packages/EAWebKit_13.4.1.0.0.zip>) and [EAWebKit-13.4.2.0.0](<http://gpl.ea.com/packages/EAWebKit_13.4.2.0.0.zip>) releases only contain PS4 and XBOX One solutions, which won't be much use to people outside of the console games development community.

Have fun, and keep your eyes peeled for new EA Open Source releases. I don't believe they are being announced in any way, which is a real shame.

EA should be boasting about these releases, not keeping them quiet, because they are fantastic.
