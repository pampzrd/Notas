#cli #api #go #code

`package main`  
  
`import (`  
    `"fmt"`  
    `"github.com/spf13/cobra"    "regexp")`  
  
`func main() {`  
    `var rootCmd = &cobra.Command{Use: "cobraCLI"}`  
    `var nome, email, senha string`  
    `var cmd = &cobra.Command{`  
       `Use:   "create",`  
       `Short: "Crie um novo usuário",`  
       `Run: func(cmd *cobra.Command, args []string) {`  
          `if nome == "" {`  
             `fmt.Println("Nome não pode estar vazio")`  
             `return`  
          `}`  
          `emailRegex := regexp.MustCompile(^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$)`  
          `if !emailRegex.MatchString(email) {`  
             `fmt.Println("Email inválido. Por favor insira um email válido.")`  
             `return`  
          `}`  
          `if len(senha) < 6 {`  
             `fmt.Println("A senha deve ter pelo menos 6 caracteres.")`  
             `return`  
          `}`  
          `fmt.Printf("Nome: %s\n Email: %s\n Senha: %s\n", nome, email, senha)`  
       `},`  
    `}`  
    `cmd.Flags().StringVarP(&nome, "nome", "n", "", "Nome do Usuário")`  
    `cmd.Flags().StringVarP(&email, "email", "e", "", "Email do Usuário")`  
    `cmd.Flags().StringVarP(&senha, "senha", "s", "", "Senha do usuário")`  
    `rootCmd.AddCommand(cmd)`  
    `rootCmd.Execute()`  
`}`  
  
`/* Os comandos serão o create e o help`  
`PS C:\Users\Pam\Go\src\PRATICANDO\CobraCLIcomCobra> .\CobraCLIcomCobra.exe create -n Chapolin -e chapolin@colorado.com -s senhadificil99Yay`  
`Nome: Chapolin`  
 `Email: chapolin@colorado.com Senha: senhadificil99Yay`  
`*/`

REF: [[https://www.youtube.com/watch?v=Ph2QEB0WMcA]]