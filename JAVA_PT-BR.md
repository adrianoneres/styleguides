# Java (Português do Brasil)

O guia foca no estilo de programação considerado ideal para manter uma padronização e facilitar a manutenção do software. Para evitar redundâncias não está coberto neste guia as definições já consolidades em convenções da linguagem, como as de nomenclatura de variáveis, métodos, classes, entre outros, que já devem ser seguidas por padrão e apenas complementadas pelas seguintes.

## 1 Metadados

### 1.1 Encoding

O código fonte deve utilizar o encoding UTF-8. Lembre de configurar a sua IDE.

### 1.2 Idioma

Deve-se seguir o idioma português para nomenclatura em geral, exceto nos casos onde esteja utilizando um padrão ou biblioteca em que a tradução comprometa o entendimento de sua aplicação.

| Tipo | Exemplo | Discussão |
| :---: | :---: | :---: |
| classe | PessoaDAO | Melhor: aplica o padrão sem traduzi-lo, o que comprometeria seu entendimento. |
| classe | PessoaOAD | Ruim: tenta traduzir o padrão _DAO_ do nome da classe para a sigla correspondente em português, comprometendo o entendimento. |
| método | getNomeFormatado | Melhor: mesmo que _nomeFormatado_ não seja um atributo da classe, pode-se aproveitar o _Duck Typing_ desta estratégia. |
| método | obterNomeFormatado | Permitido: quando se tratar de um método que não corresponde a um _getter_ de algum atributo de classe. |
| variável | escritorArquivo | Melhor: nome totalmente em português. Fácil entendimento. |
| variável | writerArquivo | Ruim: parte do nome em inglês e parte em português. |

### 1.3 Indentação

Deve-se utilizar 4 espaços para indentação dos arquivos _.java_.

### 1.4 Line-wrapping

Quando um código referente à uma única declaração é quebrado em múltiplas linhas, chamamos de _line-wrapping_.

A métrica utilizada deve ser de 150 caracteres.

É preferível que a quebra de linha seja feita pelo programador do que usando a IDE, geralmente o resultado é mais semântico.

#### 1.4.1 Onde quebrar a linha

Não existe regra definida para onde as quebras devem ocorrer, no entanto, a referência a seguir pode ser uma boa indicação.

1. Se a linha é quebrada em uma declaração que não seja de atribuição (utilizando o símbolo `=`), essa quebra deve ocorrer antes do símbolo.
    - Sendo assim, isso também se aplica para os seguintes símbolos:
        - O separador ponto ( . )
        - Os dois pontos duplos para referência de métodos ( :: )
        - O 'E comercial' em um vínculo de tipo ( `<T extends Foo & Bar>` )
        - O _pipe_ em um bloco _catch_ ( `catch (FooException | BarException e)` )
2. Se a linha é quebrada em uma declaração de atribuição (utilizando o símbolo `=`), esta quebra preferencialmente virá depois do símbolo de atribuição.
3. A assinatura de um método ou construtor permanece anexada ao parêntese de abertura ( `(` ) que corresponde à ela.
4. Uma vírgula ( `,` ) permanece anexada ao _token_ que a precede.
5. A linha nunca deve ser quebrada logo após a seta em uma expressão lâmbda, exceto se essa quebra vier imediatamente após a seta, em uma expressão lâmbda sem chaves.

Exemplo:

```java
    MinhaLambda<String, Long, Object> lambda =
        (String label, Long value, Object obj) -> {
            // corpo da expressão
        }

    Predicate<String> predicate = str ->
        longExpressionInvolving(str);
```

## 2 Formatação

### 2.1 Chaves

Chaves são utilizadas com `if`, `else`, `for`, `do` e `while` e devem ser abertas na mesma linha da assinatura destes blocos - nunca na linha seguinte.

Seu uso é opcional na seguinte situação:

#### Condição `if` com somente uma linha.

Neste caso, o corpo do bloco `if` deve conter somente uma validação e estar imediatamente à frente da linha da assinatura deste bloco - nunca na linha seguinte.

__Ruim:__ bloco sem chaves com corpo na linha seguinte. 

```java
    if(pessoa.getIdade() >= 18) 
        System.out.println("Maior de idade.");
```

Bom: bloco sem chaves com corpo enxuto à frente da assinatura do bloco.

```java
    if(pessoa.getIdade() >= 18) System.out.println("Maior de idade.");
``` 

### 2.2 Blocos vazios

Blocos vazios devem ser concisos. Não deve haver linhas em branco dentro destes blocos. Preferencialmente, a chave de encerramento do bloco deve estar imediatamente após a chave de abertura.

__Ruim:__ bloco vazio com linha em branco ou comentário no corpo.

```java
    public Pessoa() {
        
    }
```

__Bom:__ bloco vazio sem linha em branco ou comentário no corpo.

```java
    public Pessoa() {
    }
```

__Melhor:__ bloco vazio com chave de encerramento na mesma linha da assinatura, sem espaço ou comentário entre as chaves.

```java
    public Pessoa() {}
```