---
title: "Visual Studio Code For Golang"
date: 2020-06-28T22:57:00-04:00
draft: false
summary : "Step by Step guide of setting up dev environment for go"
tags : [
    "golang",
    "env-setup"
]
categories : [
    "golang"
]
series : ["environment"]
---
This article helps to get started with golang using vscode.The  go extension for vscode provides many useful features such as, auto-completion, debugging and  in-context help etc, which aids in developer productivity. 

## Install Visual Studio Code (on Mac)
To install Visual Studio Code, follow [these](https://code.visualstudio.com/docs/setup/mac) steps  

## Install Go (on Mac)
There are multiple ways to install golang
### 1) Tarball  
[Download](https://golang.org/dl/) archive and extract it lat location  `usr/local/go`. 
Detailed steps are provided [here](https://golang.org/doc/install#tarball) 
### 2) Installer  
This option entails downloading a .pkg installer for macos and following the GUI installation wizard to install go.
The steps are provided [here](https://golang.org/doc/install#macos) 
### 3) Brew  
Brew is the package manager for macOS and helps in easy installtion for third party tools, libraraies and binaries.
```bash
brew update
brew install golang
```
After install check the go is installed properly 
```
go version

go version go1.14.4 darwin/amd64
```

## Your First Program

Starting with golang version `1.13` **[Go Module](https://blog.golang.org/using-go-modules)** is default for development.It is new dependency management system which makes dependency information explicit and easier to manage - similar to maven, gradle in java land. With Modules, there is no need to have all code inside a single go-workspace and its possible to create modules in any directory.

*[VSCode Go Extension](https://code.visualstudio.com/docs/languages/go)* supports Go Modules and enables intellisense for imported packages by making use of language server and other necessary go-tools.VSCode will prompt to install the go extension and supported modules on detecting a `.go` file but, if it doesn't then we can install them manually.
- *Install go extension*
![image](/images/go-extension.png)
- *install go tools*
![alt text](/images/go-tools.png)

#### 1) Create Module
To compile and run go hello world, we must first create a module with a module-path. 
Module path is the prefix for all packages of the module.Module-path usually are in-accordance with its module's actual physically addressable location on the web when published (such as github). It can take the form like  *github.com/<user-name>/<module-name>*  for ex. `github.com/lruchandani/hello`.

Following are the steps to create a module

```
mkdir hello-world
cd hello-world
go mod init github.com/lruchandani/hello-world
```
This would create a file go.mod inside `hello-world` directory and command `cat go.mod`  would yeild.
```
module github.com/lruchandani/hello

go 1.14
```
#### 2) Write hello-world 
Create a file hello.go inside directory `hello-world` 
```go
package main

import (
	"fmt"
)

func main() {
	fmt.Println("Hello, world.")
}
```
#### 3) Open VsCode at module location
* Open terminal
* Ensure that you are in `hello-world` directory
* type `code .`  - open current directory (i.e. `hello-world`) in vscode.
* you will get the prompts to install go extension if not already installed.
* Opt to use the language server and set essential settings in vscode to enable intellisense
```
"go.autocompleteUnimportedPackages": true,
"go.docsTool": "gogetdoc",
"go.gocodeAutoBuild": true,
"go.useLanguageServer": true,
"go.formatTool": "goimports",
```
* run the program through vscode by  `^D` or by issuing following command at the terminal
```
go run github.com/lruchandani/hello-world
```
* Check that auto-complete works for third party packages  
![image](/images/go-intellisense.png)



