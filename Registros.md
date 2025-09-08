## Registros

Um registro é uma estrutura que agrupa várias informações como, por exemplo, uma ficha de registro como nome, email, idade, etc.

```
typedef struct
{
  <tipo_do_campo_1>  <campo1>
  <tipo_do_campo_2>  <campo2>
  .
  .
  .
  <tipo_do_campo_n>  <campoN>
} novo tipo;
```
- Esse "novo tipo" é o nome para essa estrutura nova que estou criando para poder identificar/chamar no meu código;

Ou
```
struct <nome_tipo>
{
  <tipo_do_campo_1>  <campo1>
  <tipo_do_campo_2>  <campo2>
  .
  .
  .
  <tipo_do_campo_n>  <campoN>
} novo tipo;

typedef struct <nome_tipo> <novo_tipo>;
```
- Já na nessa estrutura é colocado o nome anterior do tipo para o novo nome do tipo para qual ele será chamada dentro de meu código;

- As structs devem ser definidas sempre no começo do meu código, para que assim possa ficar tranquilo para poder chamá-la dentro do meu código;

Exemplo:
```C
typedef struct
{
  char nome[40];
  int idade;
  char email[40];
} regficha;
```
Ou
```C
struct ficha
{
  char nome[40];
  int idade;
  char email[40];
} regficha;

typedef struct ficha regficha;
```

E para quando for chamar ela dentro de nosso código devo declarar ela dentro do código junto das váriaveis e junto da quantidade de "fichas" que irá chamar para o código.

Exemplo:
```C
regficha ficha1, ficha2, ficha3;
```

E neste caso para sempre quando for fazer a leitura das informações após declarada o seu registro no código seria da seguinte forma:

Se caso for injetar os valores nas variáveis:
```C
strcpy(ficha1.nome, "Breno Utimura");
ficha1.cpf = 123456789;
ficha1.sexo = 'M';
ficha1.salario = 8523.28;
```

Se caso for os valores quando o usuário for digitar:
```C
scanf("%d", &ficha1.cpf);
scanf("%f", &ficha1.salario);
scanf("%s", ficha1.nome);
scanf("%c", &ficha1.sexo);
```
