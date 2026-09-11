# Factory Method - Jogo de Localizações Brasileiras

Implementação do padrão de projeto **Factory Method** utilizando um cenário de jogo de ação com diferentes localizações brasileiras.

O projeto simula um sistema onde cada região possui seus próprios tipos de inimigos, mantendo o jogador independente da lógica de criação dos objetos. Cada localização é responsável por criar o inimigo correspondente, permitindo a expansão do jogo com novas regiões e inimigos sem alterar o código existente.

## Conceitos aplicados

- **Factory Method**: separação da lógica de criação dos inimigos das regras principais do jogo.
- **Herança**: criação de diferentes tipos de inimigos a partir de uma classe abstrata.
- **Polimorfismo**: permite que o jogo trabalhe com qualquer inimigo através da abstração `Inimigo`.

## Estrutura do projeto

- `Inimigo` → Classe abstrata que define o comportamento comum dos inimigos.
- `AnimalMutante` → Inimigo específico da região Amazônia.
- `Cangaceiro` → Inimigo específico da região Sertão.
- `Localizacao` → Classe abstrata responsável pela criação dos inimigos.
- `Amazonia` → Fábrica que cria animais mutantes.
- `Sertao` → Fábrica que cria cangaceiros.
- `Main` → Simulação do funcionamento do padrão.

## Funcionamento

O jogador interage apenas com a abstração `Localizacao` e recebe um objeto do tipo `Inimigo`, sem precisar conhecer qual classe concreta será criada.

Exemplo:

```java
Localizacao localizacao = new Amazonia();

Inimigo inimigo = localizacao.criarInimigo();

System.out.println(inimigo.atacar());
