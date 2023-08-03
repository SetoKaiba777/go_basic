# Go
## _A linguagem da Google_

![N|Solid](https://www.nixsolutions.com/uploads/2020/07/Golang-700x395.png)

A linguagem Go foi criada pelo Google e foi anunciada publicamente em novembro de 2009. A motivação para sua criação foi a necessidade de uma linguagem de programação que atendesse a várias demandas específicas do Google, bem como para abordar algumas limitações e desafios encontrados em outras linguagens de programação existentes na época.

Algumas das principais motivações para a criação da linguagem Go incluem:

-   **Eficiência e Desempenho**: O Google tem uma enorme infraestrutura de sistemas distribuídos e servidores. A empresa precisava de uma linguagem que oferecesse alta eficiência e desempenho para atender às suas necessidades de escalabilidade.

-   **Simplicidade**: Muitas linguagens de programação existentes na época eram consideradas complexas e tinham uma curva de aprendizado íngreme. Go foi projetada para ser uma linguagem simples, de fácil compreensão e de leitura mais clara. Isso torna mais fácil para os desenvolvedores aprenderem, usarem e colaborarem no código.

-   **Concorrência**: A programação concorrente é crucial para sistemas distribuídos e paralelismo. Go foi projetada desde o início para oferecer suporte nativo à concorrência através das goroutines (rotinas leves) e channels (canais de comunicação).

-   **Facilidade de Manutenção**: O Google precisava de uma linguagem que permitisse que equipes grandes e distribuídas trabalhassem em projetos sem perda de produtividade. A simplicidade da sintaxe e das regras de formatação de Go facilitam a leitura e a manutenção do código em diferentes projetos.

-   **Velocidade de Compilação**: A compilação rápida é essencial para a produtividade dos desenvolvedores. Go foi projetada para ter um tempo de compilação rápido, permitindo que os desenvolvedores obtenham feedback rapidamente durante o processo de desenvolvimento.

-   **Segurança e Robustez**: A linguagem foi projetada para evitar erros comuns de programação e promover a segurança do código. Recursos como a verificação de tipos estática e tratamento explícito de erros tornam o código mais robusto.

-   **Suporte à Escalabilidade**: Go foi projetada para ser adequada para projetos pequenos e grandes. Ela deve suportar projetos em crescimento, permitindo a criação de aplicativos de qualquer escala.

## Variáveis e tipos básicos

Os tipos de dados são fundamentais na programação, pois determinam o tipo de informação que uma variável pode armazenar.  Vamos abordar alguns dos principais tipos de dados em Go:

-   **Inteiros**:   Em Go, os inteiros podem ser assinados (podem ser positivos ou negativos) ou não assinados (apenas positivos). Os principais tipos de inteiros em Go são: int, int8, int16, int32, int64, uint, uint8, uint16, uint32, uint64. A diferença entre eles é o número de bits que cada tipo ocupa na memória. Por exemplo, o tipo int geralmente ocupa 32 bits em sistemas de 32 bits e 64 bits em sistemas de 64 bits.

-    **Ponto Flutuante**:   Números de ponto flutuante são usados para representar números com partes fracionárias. Em Go, temos dois tipos principais de ponto flutuante: float32 e float64. O float32 ocupa 32 bits e o float64 ocupa 64 bits, sendo este último mais preciso e geralmente utilizado por padrão.

-    **String**:   Representa uma sequência de caracteres. As strings são imutáveis em Go, ou seja, uma vez criadas, não podem ser alteradas. Para manipulá-las, você cria novas strings com as modificações desejadas.

-    **Booleano**:   Representa valores booleanos, que podem ser true ou false.   São frequentemente usados em expressões condicionais para controlar o fluxo de execução do programa.

-    **Rune**:   Representa um valor numérico que representa um ponto de código Unicode. Geralmente é usado para representar caracteres Unicode individuais, onde rune é um alias para int32.

Agora que conhecemos os tipos, uma pergunta que você pode estar se fazendo é... Como eu armazeno um valor em uma variável? Bem, em Go existe algumas formas de se atribuir valor à uma variável, antes de entrarmos nos detalhes de implementação, vamos entender oque significa instanciar uma variável!

Instanciar uma variável significa reservar um pedaço de memória volátil para armazenar determinado valor. Uma coisa importante é que em Go, as variáveis tem uma tipagem forte, isso significa que uma vez que instanciamos uma variável, o tipo dela **JAMAIS** muda.

Podemos declarar uma variável da seguinte maneira:

    var nome tipoDaVariável
    var nome tipoDaVariável = valor

Go também tem suporte à inferencia de tipos, isso significa que a linguagem consegue entender o tipo da variável através da atribuição de valor. Podemos usar
a inferencia de tipos de duas maneiras

    var nome = valor
    nome := valor

outra coisa importante a se dizer é que existe um tipo especial de declaração para variáveis que não irão sofrer alteração de valor ao longo do código (constantes)
para isso, o Go possui a palavra reservada **const**. Para declarar uma constante devemos obedecer a seguinte sintaxe:

    const nome = valor

## Estruturas de Controle

Outro conceito fundamental é o de estruturas de controle, as esturutras de controle nos permitem validar condições booleanas e realizar repetição de código. Go é uma linguagem focada em simplicidade, e por conta disso, temos apenas 3 esturutras de controle e são elas

**For**, **Switch-Case**, **If**

O **For** é a única estrutura de repetição presente em Go, podemos usar ela de 2 formas, a primeira é para um numero fixo de repetições, conforme mostrarei no exemplo abaixo:

    for inicialização; condição; pós-execução {
        // código a ser repetido enquanto a condição for verdadeira
    }

ou 

    for condição {
        // código a ser repetido enquanto a condição for verdadeira
    }


As estruturas condicionais são Switch-Case e If e suas sintaxes são bastante simples conforme mostrado abaixo:

### Switch-Case

    switch expressão {
        case valor1:
            // código a ser executado se a expressão for igual a valor1
        case valor2:
            // código a ser executado se a expressão for igual a valor2
        default:
            // código a ser executado se nenhuma das opções anteriores for verdadeira
    }

### If

    if condição {
         // código a ser executado se a condição for true
    }

## Arrays e Slices

Em Go, temos estruturas de dados usadas para armazenar coleções de elementos do mesmo tipo e são elas as Arrays e Slices. No entanto, eles têm algumas diferenças importantes entre si em termos de tamanho, flexibilidade e comportamento. Vamos entender cada um deles:

**Array**:  Um array em Go é uma coleção fixa de elementos com tamanho definido no momento da sua declaração. Após criado, o tamanho do array não pode ser alterado.
A declaração de um array em Go segue a seguinte sintaxe:

    var nomeDoArray [tamanho]tipo

- Os índices de um array em Go vão de 0 a tamanho-1. Para acessar ou atribuir um valor a um elemento do array, você utiliza a notação de colchetes [índice]. Por Exemplo:


        var numeros [5]int // Cria um array de inteiros com tamanho 5
        numeros[0] = 10    // Atribui o valor 10 ao primeiro elemento do array (índice 0)
        fmt.Println(numeros[0]) // Imprime o valor 10


**Slice**: Um slice em Go é uma estrutura dinâmica que se comporta como uma "fatia" de um array subjacente. Diferente de um array, o tamanho de um slice pode mudar dinamicamente. A declaração de um slice em Go segue a seguinte sintaxe:

        var nomeDoSlice []tipo

-   eles não possuem tamanho definido na declaração e podem ser criados a partir de um array existente ou usando a função make.

        // Criando um slice a partir de um array existente
        arr := [5]int{1, 2, 3, 4, 5}
        slice := arr[1:4] // slice contém [2, 3, 4]
        // Criando um slice usando a função make
        slice := make([]int, 3) // Cria um slice de inteiros com tamanho 3 e valores iniciais 0
    
-   Sua composição é feita de um ponteiro para o array subjacente, o tamanho do slice e a capacidade do array subjacente (o número de elementos desde o início do  slice até o final do array). Por ser uma "fatia" de um array, as modificações em um slice afetam o array original, e vice-versa.

## Funções

Em Go, as funções são blocos de código que executam uma tarefa específica e podem ser chamadas a partir de outros lugares no programa. As funções são fundamentais  para organizar e modularizar o código, tornando-o mais legível, reutilizável e fácil de manter. Vamos explorar os principais aspectos das funções em Go:

A sintaxe para declarar uma função em Go é a seguinte:

    func nomeDaFuncao(parametros) tipoDoRetorno {
        // corpo da função
        return valorDeRetorno
    }

é importante ressaltar que em Go, podemos ter mais de um retorno em uma única função. Go permite funções de multiplo retorno, vamos a um exemplo de implementação e chamada de função

    func saudacao(nome string) {
        fmt.Println("Olá, " + nome + "!")
    }
    saudacao("Caio") // executa o código  fmt.Println("Olá, " + "Caio" + "!")

além disso, a linguagem também possui suporte para funções com um número variável de argumentos. Isso é feito usando três pontos (...) após o tipo do último parâmetro. 
Exemplo:

    func somaVariadica(nums ...int) int {
        total := 0
        for _, num := range nums {
            total += num
        }
        return total
    }
    
    somaVariadica(1, 2, 3) // Retorna 6 
    somaVariadica(10, 20, 30, 40, 50) // Retorna 150

Go possui um outro recurso bastante utilizado em outras linguagens, que é a possibilidade de criação de uma função anônima. Uma função anônima não possui um nome e pode ser atribuída a variáveis, passadas como argumentos para outras funções e até mesmo retornadas como resultados de outras funções.
Exemplo:

    func multiplicador(x int) func(int) int {
        return func(y int) int {
            return x * y
        }
    }

    dobro := multiplicador(2)
    resultado := dobro(5) // Retorna 10

