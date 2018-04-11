# Java Style Guide

O guia foca no estilo de programação considerado ideal para manter uma padronização e facilitar a manutenção do software. Para evitar redundâncias não está coberto neste guia as definições já consolidades em convenções da linguagem, como as de nomenclatura de variáveis, métodos, classes, entre outros, que já devem ser seguidas por padrão e apenas complementadas pelas seguintes.

## 1 Código fonte

### 1.1 Encoding

O código fonte deve utilizar o encoding UTF-8. Lembre de configurar a sua IDE.

## 2 Estilos de programação

### 2.1 Idioma

Deve-se seguir o idioma português para nomenclatura em geral, exceto nos casos onde esteja utilizando um padrão ou biblioteca em que a tradução comprometa o entendimento de sua aplicação.

| Tipo | Exemplo | Discussão |
| :---: | :---: | :---: |
| classe | PessoaDAO | Melhor: aplica o padrão sem traduzi-lo, o que comprometeria seu entendimento. |
| classe | PessoaOAD | Ruim: tenta traduzir o padrão _DAO_ do nome da classe para a sigla correspondente em português, comprometendo o entendimento. |
| método | obterNomeFormatado | Melhor: quando se tratar de um método que não corresponde a um _getter_ de algum atributo de classe. |
| método | getNomeFormatado | Permitido: no caso em que _nomeFormatado_ seja um atributo e este nome seja apenas a implementação do _getter_ deste atributo. |
| variável | escritorArquivo | Melhor: nome totalmente em português. Fácil entendimento. |
| variável | writerArquivo | Ruim: parte do nome em inglês e parte em português. |
