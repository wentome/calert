# calert

```package main

import (
	"calert"
	"flag"
	"log"
)

func main() {
	flag.Parse()
	flagArgs := flag.Args()
	if len(flagArgs) == 3 {
		ealert := calert.NewAlert("http://localhost:8888/alert", flagArgs[0])
		res, err := ealert.Send(flagArgs[1], flagArgs[2])
		if err != nil {
			log.Println(err)
		} else {
			log.Println(res)
		}
	}
}```
