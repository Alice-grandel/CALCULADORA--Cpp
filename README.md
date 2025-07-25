# 🧠 Exercícios de Lógica de Programação em Rust <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/20/Rustacean-orig-noshadow.svg/320px-Rustacean-orig-noshadow.svg.png" width="40" alt="Rustacean" title="Rust" />


Este repositório contém exercícios de lógica de programação que estou resolvendo para treinar minha base em desenvolvimento e fortalecer meu raciocínio lógico, usando a linguagem **Rust**.

---

## ✍️ Objetivo

Praticar lógica de programação e registrar minha evolução nos estudos com Rust. Aqui você encontrará exercícios envolvendo:

- Variáveis e tipos de dados em Rust
- Condicionais (`if`, `else`)
- Laços de repetição (`for`, `loop`)
- Funções
- Vetores (`Vec<T>`)
- Desafios diversos de lógica

---

# EXERCICIOS RUST: 1

CALCULADORA SIMPLES:

Crie um programa que funcione como uma calculadora básica, realizando operações matemáticas entre dois números fornecidos pelo usuário.
Funcionalidades:

    Solicitar ao usuário que digite dois números.

    Solicitar qual operação matemática deseja realizar:

        Soma (+)

        Subtração (-)

        Multiplicação (*)

        Divisão (/)

    Realizar a operação escolhida e mostrar o resultado.

    Caso o usuário escolha uma operação inválida, exibir uma mensagem de erro.

    Perguntar ao usuário se deseja realizar outra operação, repetindo o processo enquanto desejar.

 # Codigo:    
<img width="2656" height="2824" alt="calculadora" src="https://github.com/user-attachments/assets/2f92142a-5ddc-4f03-8f36-f0d79413c8e9" />



## 🚀 Como estou estudando

Estou estudando Rust diariamente, resolvendo exercícios passo a passo e aplicando boas práticas de código mesmo em problemas simples. A ideia é evoluir gradualmente e usar este repositório para acompanhar meu progresso.

---

## 📌 Observações

- Todos os exercícios foram feitos por mim, com base em listas de lógica e desafios disponíveis na internet ou criados por mim mesma.
- O foco é o **aprendizado**, então nem sempre o código será o mais otimizado — o importante é que funcione e eu entenda o que está acontecendo.


# EXERCICIO RUST: 2

FOLHA DE PAGAMENTO:

Faça um programa para cálculo de uma folha de pagamento, considerando os seguintes descontos e regras:

    Imposto de Renda (IR) descontado conforme tabela do salário bruto:

        Até R$ 900,00 (inclusive): isento

        Até R$ 1500,00 (inclusive): 5%

        Até R$ 2500,00 (inclusive): 10%

        Acima de R$ 2500,00: 20%

    Desconto de 10% para o INSS.

    FGTS corresponde a 11% do salário bruto, mas não é descontado do trabalhador — é um depósito feito pela empresa.

    O salário líquido é o salário bruto menos os descontos (IR + INSS).

O programa deverá solicitar ao usuário:

    Valor da hora trabalhada.

    Quantidade de horas trabalhadas no mês.

    Exemplo de saída: 
    Salário Bruto:                 : R$ 1100,00
    IR (5%)                       : R$   55,00
    INSS (10%)                    : R$  110,00
    FGTS (11%)                    : R$  121,00
    Salário Líquido               : R$  935,00

# Codigo:     
<img width="2656" height="2464" alt="folhadepagamento" src="https://github.com/user-attachments/assets/747eba0b-ab29-49ed-bf8f-14ba41b1347d" />


# EXERCICIO RUST: 3

TABUADA: Desenvolva um programa que faça a tabuada de um número qualquer inteiro que será digitado pelo usuário, mas a tabuada não deve necessariamente iniciar em 1 e terminar em 10, o valor inicial e final devem ser informados também pelo usuário, conforme exemplo abaixo:
```
Montar a tabuada de: 5
Começar por: 4
Terminar em: 7

Vou montar a tabuada de 5 começando em 4 e terminando em 7:
5 X 4 = 20
5 X 5 = 25
5 X 6 = 30
5 X 7 = 35
```
CODIGO:
<img width="2368" height="1744" alt="tabuada" src="https://github.com/user-attachments/assets/fa91e463-5288-4eec-8150-42b96023c298" />

# EXERCICIO RUST: 4

CAIXA ELETRONICO: Faça um Programa para um caixa eletrônico.
```
O programa deverá perguntar ao usuário a valor do saque e depois informar quantas notas de cada valor serão fornecidas.

As notas disponíveis serão as de 1, 5, 10, 50 e 100 reais. O valor mínimo é de 10 reais e o máximo de 600 reais.

O programa não deve se preocupar com a quantidade de notas existentes na máquina.

Exemplo 1: Para sacar a quantia de 256 reais, o programa fornece duas notas de 100, uma nota de 50, uma nota de 5 e uma nota de 1;

Exemplo 2: Para sacar a quantia de 399 reais, o programa fornece três notas de 100, uma nota de 50, quatro notas de 10, uma nota de 5 e quatro notas de 1.
```
CODIGO:

```
use std::io;

fn main() {


    loop {

        // apresentação do programa
        println!("\nCAIXA-ELETRONICO]\n");
        println!("\nnotas disponiveis: 100 reais , 50 reais, 20 reais , 10 reais, 5 reais, 1 real\n");

        // input que pede ao usuario pra escrever o valor que deseja sacar
        let saque = read_number("\nQuanto você deseja sacar? valor de R$10.0 reais a R$600.0 reais disponiveis\n");

        // operção que diz quantas notas vão ser fornecidas
        if saque >= 10 && saque <= 600 {
          println!("Saque autorizado de {} reais ", saque);

          let mut valor_restante = saque;
          
            let nota100 = valor_restante / 100;
             valor_restante %= 100;
            
            let nota50 = valor_restante / 50;
             valor_restante %= 50;
            
            let nota20 = valor_restante / 20;
             valor_restante %= 20;

            let nota10 = valor_restante / 10; 
             valor_restante %= 10;
            
            let nota5 = valor_restante / 5;
             valor_restante %= 5;

            let nota1 = valor_restante / 1;
             valor_restante %= 1; 


             println!("[NOTAS-FORNECIDAS!]");
             read_nota(nota100, 100);
             read_nota(nota50, 50);
             read_nota(nota20, 20);
             read_nota(nota10, 10);
             read_nota(nota5, 5);
             read_nota(nota1, 1);

              if valor_restante > 0 {
                println!("n foi possivel fornecer notas para R${} de reais", valor_restante);
            }
        } else {

            println!("Valor invalido tente algo entre 10 a 600 reais");
        }


        println!("---------------------------------------------");

            // loop pra repetir o programa ou encerrar
            println!("Deseja voltar e recomeçar a operação [S/N]?");
            let mut respostas = String::new();
             io::stdin().read_line(&mut respostas).expect("Erro");

            if respostas.trim().eq_ignore_ascii_case("n") {
                println!("operação encerrada");
                break;
            }
        }

}


// função das notas
fn read_nota(quantidade: i32, valor: i32) {
    if quantidade > 0 {
        println!("{} notas fornecidas de {} reais", quantidade, valor);
    }
}

// função do input
fn read_number(prompt: &str) -> i32 {
    loop {
        println!("{}", prompt);
         let mut input = String::new();
          io::stdin().read_line(&mut input).expect("Erro");

          match input.trim().parse::<i32>() {
            Ok(num) => return num,
            Err(_) => println!("Valor invalido"),
          }
    }
}
```

# EXERCICIO RUST: 5 

CAIXA REGISTRADORA: Crie um programa em Rust que simule o funcionamento de um caixa registradora. O sistema deve permitir o registro de múltiplos produtos em uma única compra, calcular o valor total, receber o pagamento do cliente, verificar se o valor é suficiente e calcular o troco. Ao final da operação, o programa deve perguntar se o caixa deve ser reaberto para uma nova compra. 



```
use std::io;

fn main() {

    loop {

        println!("[CAIXA-REGISTRADORA!]");

        let mut total: f64 = 0.0;
        let mut produto_num = 1;
    loop {
        let preco = read_number(&format!("produto {}: ", produto_num));

        if preco == 0.0 {
            break;
        } 
            total += preco;
            produto_num += 1;
    }

         println!("Total:  R${} reais", total);

         let dinheiro = read_number("Dinheiro: R$");

         if dinheiro < total {
            println!("Compra n pode ser realizada dinheiro insuficiente");
         } else {
             let troco = dinheiro - total;
             println!("Troco do cliente:  R${} reais", troco);
          }

          

        println!("--------------------------------------------");
        println!("gostaria de recomeçar [S/N]?");
         let mut respostas = String::new();
          io::stdin().read_line(&mut respostas).expect("Erro");

          if respostas.trim().eq_ignore_ascii_case("n") {
            println!("caixa fechado");
            break;
        }
    }
}

fn read_number(prompt: &str) -> f64 {
    loop{
        println!("{}", prompt);
         let mut input = String::new();
          io::stdin().read_line(&mut input).expect("Valor invalido");

          match input.trim().parse::<f64>() {
            Ok(num) => return num,
            Err(_) => println!("Erro"),
          }
    }
}
```
# EXERCICIO RUST: 6

LITRO COMBUSTIVEL: 
 Um posto está vendendo combustíveis com a seguinte tabela de descontos: Álcool: até 20 litros, desconto de 3% por litro acima de 20 litros, desconto de 5% por litro Gasolina: até 20 litros, desconto de 4% por litro acima de 20 litros, desconto de 6% por litro
Escreva um algoritmo que leia o número de litros vendidos, o tipo de combustível (codificado da seguinte forma: A-álcool, G-gasolina), calcule e imprima o valor a ser pago pelo cliente sabendo-se que o preço do litro da gasolina é R$ 2,50 o preço do litro do álcool é R$ 1,90.

```
use std::io;

fn main() {

    loop{

        let a = 1.90;
        let g = 2.50;

        let tipo_combustivel = combustivel("Qual tipo de combustivel você deseja [A/G]");
        let litro_vendido = read_number("quantos litros de combustivel foram vendidos?");

        let preco_final = match tipo_combustivel {
            'A' | 'a' => {
                        if litro_vendido <= 20.0 {
                            a * litro_vendido * 0.97
                        } else {
                            a * litro_vendido * 0.95
                        }
                   }
            'G' | 'g' => {
                        if litro_vendido <= 20.0 {
                            g * litro_vendido * 0.96
                        } else {
                            g * litro_vendido * 0.94
                        }
                 }
                 _ => 0.0
        };

        println!("Preço total:  R${:.2} reais", preco_final);

        println!("\nGostaria de recomeçar [S/N]?\n");
        let mut resposta = String::new();
        io::stdin().read_line(&mut resposta).expect("Erro");

        if resposta.trim().eq_ignore_ascii_case("n") {
            println!("[PROGRAMA-FECHADO!]");
            break;
        }

    }

}

fn combustivel(prompt: &str) -> char {
    loop {
        println!("{}", prompt);
         let mut input = String::new();
          io::stdin().read_line(&mut input).expect("Erro");

         let combustivel = input.trim().chars().next();

        match combustivel {
            Some('A') | Some('a') | Some('g') | Some('G') => return combustivel.unwrap(),
            _ => println!("operação invalida"),
         }

    }
}

fn read_number(prompt: &str) -> f64 {
    loop {
        println!("{}", prompt);
         let mut input = String::new();
          io::stdin().read_line(&mut input).expect("Erro");

        match input.trim().parse::<f64>() {
            Ok(num) => return num,
            Err(_) => println!("Valor invalido"),
        }
    }
}
```

# EXERCICIO RUST: 7

Um jogo da forca simples feito em Rust rodando no terminal. O objetivo é adivinhar a palavra secreta, letra por letra, com no máximo 3 erros.

---

## 🦀 Tecnologias usadas

- Linguagem: **Rust**
- Conceitos utilizados:
  - `Vec` (vetores)
  - `loop`
  - `funções`
  - `match`
  - `chars()`
  - Entrada e saída com `stdin`
  - Controle de fluxo (`if`, `for`, `break`)
 
# CODIGO JOGO DA FORCA:
<img width="2476" height="2644" alt="forca" src="https://github.com/user-attachments/assets/ceb78200-da80-4698-a59b-cea2a8fa0909" />

# EXERCICIO RUST: 8

Este é um jogo da velha (tic-tac-toe) feito em **Rust**, rodando inteiramente no terminal. Dois jogadores se revezam jogando, inserindo as coordenadas da linha e coluna para marcar `X` ou `O` em um tabuleiro 3x3.

## 💡 Funcionalidades

- ✅ Interface de texto simples no terminal
- ✅ Validação de jogadas (evita sobrescrever posições)
- ✅ Verificação automática de vitória e empate
- ✅ Alternância automática entre os jogadores `X` e `O`

## 📷 Exemplo de uso

```bash
  0 1 2
0 _ _ _
1 _ _ _
2 _ _ _

Vez do jogador 'X'
Digite a linha e coluna (ex: 0 1): 1 1
```
# CODIGO JOGO DA VELHA 🦀: 

```
use std::io;

fn main() {
    let mut board = [[' '; 3]; 3];
    let mut current_player = 'X';

    loop {
        print_board(&board);
        println!("Vez do jogador '{}'", current_player);
        
      let (row , col) = get_move();

      if board[row][col] != ' ' {
        println!("Posição ja ocupada tente novamente!");
           continue;
        }
    
    
    board[row][col] = current_player;

    if check_winner(&board, current_player) {
        print_board(&board);
        println!("Jogador '{}' venceu", current_player);
           continue;
    }

    if board_full(&board) {
       print_board(&board);
        println!("Empate");
           continue;
      
    }
      current_player = if current_player == 'X' { 'O' } else { 'X' };
    
  }
}

fn print_board(board: &[[char; 3]; 3]) {
    println!("\n 0 1 2");
     for (i, row) in board.iter().enumerate() {
        print!("{}", i);
     for &cell in row.iter() {
        print!("{}", cell);
     }   
    println!();
     }
    println!();
}

fn get_move() -> (usize, usize) {
    loop {
      println!("Digite a linha e coluna (Ex: 0 1): ");
       let mut input = String::new();
        io::stdin().read_line(&mut input).expect("Erro");

       let parts: Vec<&str> = input.trim().split_whitespace().collect();
        if parts.len() != 2 {
            println!("Entrada invalida!");
             continue;
        }

       let row: usize = match parts[0].parse() {
         Ok(num) if num < 3 => num,
          _ => {
            println!("Linha invalida");
             continue;
          }
       };

       let col: usize = match parts[1].parse() {
         Ok(num) if num < 3 => num,
          _ => {
            println!("Valor invalido!");
             continue;
          }
       };

       return(row, col);
    }
}

fn check_winner(board: &[[char; 3]; 3], player: char) -> bool {
  for i in 0..3 {
    if (board[i][0] == player && board[i][1] == player && board[i][2] == player) ||
       (board[0][i] == player && board[1][i] == player && board[2][i] == player) {
         return true;
       }
  }
    if (board[0][0] == player && board[1][1] == player && board[2][2] == player) ||
       (board[0][2] == player && board[1][1] == player && board[2][0] == player) {
         return true;
       }
    false
}

fn board_full(board: &[[char; 3]; 3]) -> bool {
    for row in board {
     for cell in row {
       if *cell == ' ' {
         return false;
       }
     }
  }
    true
}
```

# EXERCICIO RUST: 9
Faça um Programa que pergunte em que turno você estuda. Peça para digitar M-Manhã ou t-TARDE ou N- noite.

Imprima a mensagem "Bom Dia!", "Boa Tarde!" ou "Boa Noite!" ou "Valor Inválido!", conforme o caso.

🦀 CODIGO: 
```
use std::io;

fn main() {

    let turno = obter_letra("Qual turno da escola vc estuda? (M = Manhã/T = Tarde/N = Noite)");

     match turno {
      'm' | 'M' => println!("Tenha um Bom dia!"),
      't' | 'T' => println!("Tenha uma Boa tarde!"),
      'n' | 'N' => println!("Tenha uma Boa noite!"),
         
          _ => println!("Valor invalido"),
     };
}

fn obter_letra(prompt: &str) -> char {
  loop {
        println!("{}", prompt);
         let mut entrada = String::new();
          io::stdin().read_line(&mut entrada).expect("Erro");

        let turno = entrada.trim().chars().next();
        
       match turno {
        Some('m') | Some('M') | Some('T') | Some('t') | Some('n') | Some('N') => return turno.unwrap(),
         _ => {
             println!("Letra invalida!");
         }
       } 
    }
}
```
