Go or Golang is a relatively new language developed by the geniuses over at Google, it's a small, exciting and incredibly fast language that has seen a massive growth in it's popularity.

I'm not a Go expert, and I'm not going to cover the whole language but I would like to show you why Go may be the next language for you to learn and add to your skillset.

# Before we start

In this tutorial I'm going to assume you have Go installed already and have set your `$GOPATH`. Don't worry if you haven't installed Go, just head over to the [Go website](https://golang.org/doc/install) to install Go on your machine.

# Let's Go!

Go is a very simple language to get started with.

Create a folder call `hello-world` and then move into this folder `cd hello-world`. Once inside the folder create a file called `hello-world.go`. You can create this file inside your preferred text editor or with the command line using `touch hello-world.go`. Go ahead and open the file we just created.

A fresh blank Go file. Let's get started by adding the following to create the famous "Hello World!" file:

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello World!")
}
```

If you have experience with another language you will probably be able to make sense of some of this code. We'll break it down anyway.

- `package main`: This line is important to the file as the first line in any Go executable file must be a `package` statement. As this file is an executable it will be using the `main` package to tell the Go compiler that we want this file to be executable.

- `import "fmt"`: Here we're importing the fmt package. This package implements formatted I/O. So, this gives us functions like `Println()` and `Printf()`.

- `func main() {}`: This is our main function that is executed first by the program.

- `fmt.Println()`: Finally, inside our `main()` function we're using the `Println()` method from our `fmt` package. We're accessing this method using the dot notation, then passing our string of "Hello World!" to the `Println()`.

Open up your terminal, and head into the folder containing your `hello-world.go` file. Run `go build`, don't worry Go is super fast so your code will be compiled before you can blink. Now, to run our masterpiece, in your terminal type `./hello-world`. Make sure to leave the `.go` of the end. This command will run the executable file that `go build` created. Voila! Inside your terminal you should see "Hello World", great isn't it?
Well, its not the most amazing thing that you've ever seen but it's Go. That is it for this post but don't worry we will dive into more of the magic of Go in future tutorials.
