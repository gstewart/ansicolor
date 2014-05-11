# ansicolor

Ansicolor library provides color console in Windows as ANSICON for Golang.

## Features

|Escape sequence|Text attributes|
|---------------|----|
|\x1b[0m|All attributes off(foreground white and background black)|
|\x1b[1m|Bold on(intensity)|

|Escape sequence|Foreground colors|
|---------------|----|
|\x1b[30m|Black|
|\x1b[31m|Red|
|\x1b[32m|Green|
|\x1b[33m|Yellow|
|\x1b[34m|Blue|
|\x1b[35m|Magenta|
|\x1b[36m|Cyan|
|\x1b[37m|White|
|\x1b[39m|Default(white)|

|Escape sequence|Background colors|
|---------------|----|
|\x1b[40m|Black|
|\x1b[41m|Red|
|\x1b[42m|Green|
|\x1b[43m|Yellow|
|\x1b[44m|Blue|
|\x1b[45m|Magenta|
|\x1b[46m|Cyan|
|\x1b[47m|White|
|\x1b[49m|Default(black)|

## Example

```go
package main

import (
	"fmt"
	"os"

	"github.com/shiena/ansicolor"
)

func main() {
	w := ansicolor.NewAnsiColorWriter(os.Stdout)
	text := "%sforeground %sbold%s %sbackground%s\n"
	fmt.Fprintf(w, text, "\x1b[31m", "\x1b[1;31m", "\x1b[0m", "\x1b[41;32m", "\x1b[0m")
	fmt.Fprintf(w, text, "\x1b[32m", "\x1b[1;32m", "\x1b[0m", "\x1b[42;31m", "\x1b[0m")
	fmt.Fprintf(w, text, "\x1b[33m", "\x1b[1;33m", "\x1b[0m", "\x1b[43;34m", "\x1b[0m")
	fmt.Fprintf(w, text, "\x1b[34m", "\x1b[1;34m", "\x1b[0m", "\x1b[44;33m", "\x1b[0m")
	fmt.Fprintf(w, text, "\x1b[35m", "\x1b[1;35m", "\x1b[0m", "\x1b[45;36m", "\x1b[0m")
	fmt.Fprintf(w, text, "\x1b[36m", "\x1b[1;36m", "\x1b[0m", "\x1b[46;35m", "\x1b[0m")
	fmt.Fprintf(w, text, "\x1b[37m", "\x1b[1;37m", "\x1b[0m", "\x1b[47;30m", "\x1b[0m")
}
```

## See also:

- https://github.com/daviddengcn/go-colortext
- https://github.com/adoxa/ansicon
- https://github.com/aslakhellesoy/wac
- https://github.com/wsxiaoys/terminal

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
