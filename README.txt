First you need to give this permission to admin user, "Administer basic redirect".


If you happen to lock your self out, this module configuration page would still
be available at `/admin/build/basic-redirect`.


Sample configurations:

    /^\/welcome-pro-play-sportswear/  301  http://example.com
    /^\/shirt-styles/                 301  http://example.com
    /^\/(.*)/                         301  http://example.com/$1

It's divided into 3 parts:

 a) match pattern (regex)
 b) return code (http code, 301 for example means permanent redirect)
 c) replacement pattern (regex)

For more details see PHP preg_replace() documentation.


Notice that the first characters of match pattern consist of:

 * `/` and its pair at the end, means the character used to enclose the regex
   pattern.
 * `^` means start of sentence (in regex).
 * `\/` means path separator, forward slash (escaped using backslash), because
   this module looks for `$_SERVER['REQUEST_URI']` which  usually return something
   like `/path`.
