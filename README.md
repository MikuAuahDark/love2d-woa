love2d-woa
=====

GitHub Actions Steps to compile LÖVE for Windows 10 ARM64

See my efforts of my porting blog post in here: [part 1][p1], [part 2][p2], [part 3][p3]

Platform Difference
-----

LÖVE on Windows 10 ARM64 can't use LuaJIT at the moment because [LuaJIT/LuaJIT#593][ljissue].
Furthermore, OpenGL (let alone WGL) is unavailable so [ANGLE][angle] must be used.

To polyfill the `bit` library (which supposed to be LuaJIT built-in), it must be compiled and
placed alongside the LÖVE executable, same goes to ANGLE. Then shipped along.

[p1]: https://auahdark687291.blogspot.com/2020/11/love-on-windows-10-arm64-part-1.html
[p2]: https://auahdark687291.blogspot.com/2020/11/love-on-windows-10-arm64-part-2-one.html
[p3]: https://auahdark687291.blogspot.com/2020/11/love-on-windows-10-arm64-part-3-were.html
[ljissue]: https://github.com/LuaJIT/LuaJIT/issues/593
[angle]: https://chromium.googlesource.com/angle/angle
