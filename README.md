## About
Brainfuck-Go is a [Brainfuck](http://en.wikipedia.org/wiki/Brainfuck) interpreter written in Go.

## Usage

```Golang

package main

import (
	"fmt"
	"io/ioutil"
	"os"

	bf "github.com/837278709/brainfuck-go"
)

func main() {
	args := os.Args
	if len(args) != 2 {
		fmt.Printf("Usage: %s filename\n", args[0])
		return
	}
	filename := args[1]
	fileContents, err := ioutil.ReadFile(filename)
	if err != nil {
		fmt.Printf("Error reading %s\n", filename)
		return
	}
	bf.RunBF(fileContents)
}

```

```
curl -s "http://www.99-bottles-of-beer.net/download/1718" > bottles.bf
./main bottles.bf
```
## License
[The MIT License (MIT)](http://opensource.org/licenses/mit-license.php)
