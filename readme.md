# Link Parser for JavaScript

This:

```
link a/b[c/d][e]/f[g[h[i/j]]]
  text <foo {bar(<hello {random}>, <world>)} baz>
  another bar

x foo/bar, foo/baz, a/b/c
y <foo>, 123, #u123, 3.14
dynamic-{term(<asdf>)} foo
{one}{two}-three{four(x)}-five
```

Becomes this:

<!-- prettier-ignore -->
```json
{
  "form": "site",
  "host": [
    {
      "form": "term",
      "link": [
        {
          "form": "cord",
          "cord": "file" } ] } ],
  "site": [
    {
      "form": "site",
      "host": [
        {
          "form": "term",
          "link": [
            {
              "form": "cord",
              "cord": "link" } ] } ],
      "site": [
        {
          "form": "site",
          "host": [
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "a" } ] },
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "b" } ] },
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "c" } ] },
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "d" } ] } ],
              "site": [] },
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "e" } ] } ],
              "site": [] },
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "f" } ] },
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "g" } ] },
                {
                  "form": "site",
                  "host": [
                    {
                      "form": "term",
                      "link": [
                        {
                          "form": "cord",
                          "cord": "h" } ] },
                    {
                      "form": "site",
                      "host": [
                        {
                          "form": "term",
                          "link": [
                            {
                              "form": "cord",
                              "cord": "i" } ] },
                        {
                          "form": "term",
                          "link": [
                            {
                              "form": "cord",
                              "cord": "j" } ] } ],
                      "site": [] } ],
                  "site": [] } ],
              "site": [] } ],
          "site": [] },
        {
          "form": "site",
          "host": [
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "text" } ] } ],
          "site": [
            {
              "form": "site",
              "host": [
                {
                  "form": "text",
                  "link": [
                    {
                      "form": "cord",
                      "text": "foo " },
                    {
                      "form": "site",
                      "host": [
                        {
                          "form": "term",
                          "link": [
                            {
                              "form": "cord",
                              "cord": "bar" } ] } ],
                      "site": [
                        {
                          "form": "site",
                          "host": [
                            {
                              "form": "text",
                              "link": [
                                {
                                  "form": "cord",
                                  "text": "hello " },
                                {
                                  "form": "site",
                                  "host": [
                                    {
                                      "form": "term",
                                      "link": [
                                        {
                                          "form": "cord",
                                          "cord": "random" } ] } ],
                                  "site": [] } ] } ],
                          "site": [] },
                        {
                          "form": "site",
                          "host": [
                            {
                              "form": "text",
                              "link": [
                                {
                                  "form": "cord",
                                  "text": "world" } ] } ],
                          "site": [] } ] },
                    {
                      "form": "cord",
                      "text": " baz" } ] } ],
              "site": [] } ] },
        {
          "form": "site",
          "host": [
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "another" } ] } ],
          "site": [
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "bar" } ] } ],
              "site": [] } ] } ] },
    {
      "form": "site",
      "host": [
        {
          "form": "term",
          "link": [
            {
              "form": "cord",
              "cord": "x" } ] } ],
      "site": [
        {
          "form": "site",
          "host": [
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "foo" } ] },
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "bar" } ] } ],
          "site": [] },
        {
          "form": "site",
          "host": [
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "foo" } ] },
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "baz" } ] } ],
          "site": [] },
        {
          "form": "site",
          "host": [
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "a" } ] },
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "b" } ] },
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "c" } ] } ],
          "site": [] } ] },
    {
      "form": "site",
      "host": [
        {
          "form": "term",
          "link": [
            {
              "form": "cord",
              "cord": "y" } ] } ],
      "site": [
        {
          "form": "site",
          "host": [
            {
              "form": "text",
              "link": [
                {
                  "form": "cord",
                  "text": "foo" } ] } ],
          "site": [] },
        {
          "form": "site",
          "host": [
            {
              "form": "mark",
              "mark": 123 } ],
          "site": [] },
        {
          "form": "site",
          "host": [
            {
              "form": "code",
              "base": "u",
              "code": "123" } ],
          "site": [] },
        {
          "form": "site",
          "host": [
            {
              "form": "comb",
              "fill": 3.14 } ],
          "site": [] } ] },
    {
      "form": "site",
      "host": [
        {
          "form": "term",
          "link": [
            {
              "form": "cord",
              "cord": "dynamic-" },
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "term" } ] } ],
              "site": [
                {
                  "form": "site",
                  "host": [
                    {
                      "form": "text",
                      "link": [
                        {
                          "form": "cord",
                          "text": "asdf" } ] } ],
                  "site": [] } ] } ] } ],
      "site": [
        {
          "form": "site",
          "host": [
            {
              "form": "term",
              "link": [
                {
                  "form": "cord",
                  "cord": "foo" } ] } ],
          "site": [] } ] },
    {
      "form": "site",
      "host": [
        {
          "form": "term",
          "link": [
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "one" } ] } ],
              "site": [] },
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "two" } ] } ],
              "site": [] },
            {
              "form": "cord",
              "cord": "-three" },
            {
              "form": "site",
              "host": [
                {
                  "form": "term",
                  "link": [
                    {
                      "form": "cord",
                      "cord": "four" } ] } ],
              "site": [
                {
                  "form": "site",
                  "host": [
                    {
                      "form": "term",
                      "link": [
                        {
                          "form": "cord",
                          "cord": "x" } ] } ],
                  "site": [] } ] },
            {
              "form": "cord",
              "cord": "-five" } ] } ],
      "site": [] } ] }
```
