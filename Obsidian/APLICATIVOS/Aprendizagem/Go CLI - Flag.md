#go #cli #desktop #code

`package main`  
  
`import (`  
    `"flag"`  
    `"fmt")`  
  
`// Usando Cobra para fazer um programa em CLI. Comandos no terminal.`  
`func main() {`  
    `//Flag é uma biblioteca do Go para fazer comandos cli  String> 1)Nome do valor 2)Valor 3)Definição do valor`  
    `//Então ele precisará estar dentro de um ponteiro ComandoBaby    ComandoBaby := flag.String("charactersName", "Nacho", "Nome do personagem")`  
    `flag.Parse()              //Para cozinhar os comandos a serem usados`  
    `fmt.Println(*ComandoBaby) //Vai pegar o valor do ponteiro`  
    `//Se der  um build no linux ele vai criar um executável .sh e no windows .exe    //Só executando ele exibe o valor default    /*PS C:\Users\Pam\Go\src\PRATICANDO\CobraCLI> .\CobraCLI.exe`  
    `* Nacho    // Definindo o valor novo pelo terminal >    * PS C:\Users\Pam\Go\src\PRATICANDO\CobraCLI> .\CobraCLI.exe -charactersName Titi    * Titi`

		  //Ao usar --help ele exibe quais comandos ele espera:
    `PS C:\Users\Pam\Go\src\PRATICANDO\CobraCLI> .\CobraCLI.exe --help
    `Usage of C:\Users\Pam\Go\src\PRATICANDO\CobraCLI\CobraCLI.exe:`
    `-charactersName string`
        `Nome do personagem (default "Nacho")`

    */
    
    }`

REF: [[https://www.youtube.com/watch?v=Ph2QEB0WMcA]]