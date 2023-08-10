

---==--==---

To create a "Hello, World!" application in Lisp, you can use the `write-line` function to print the text to the console. Here's an example:

```lisp
(defun hello-world ()
  (write-line "Hello, World!"))

(hello-world)
```

This code defines a function called `hello-world` that simply writes the "Hello, World!" string to the console using `write-line`. The final line `(hello-world)` calls the function and executes the code.

To run this Lisp program, you can use any compatible Lisp interpreter. For example, you can use the popular Common Lisp implementation called SBCL (Steel Bank Common Lisp). To install SBCL, you can use package managers like Homebrew (on macOS) or apt-get (on Ubuntu).

Once installed, you can save the code in a file, for example, `hello.lisp`, and run it using the `sbcl` command:

```bash
sbcl --script hello.lisp
```

Running this command will output:

```
Hello, World!
```

---==--==---

Create a hello world Lisp app
