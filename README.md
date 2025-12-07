# Algoritmo Genético - Otimização de Build de Personagem RPG

## 📋 Sobre o Projeto

Trabalho acadêmico desenvolvido para a disciplina de **Técnicas de Programação Avançada** do curso de Sistemas de Informação no Campus Cachoeiro de Itapemirim.

Este projeto implementa um Algoritmo Genético para otimizar a distribuição de atributos e habilidades de personagens em jogos RPG, buscando maximizar a eficiência em combate através de simulações.

## 👥 Autores

- **Bruna Cedro**
- **Larissa Paganini**

## 🎯 Objetivo

Criar builds otimizadas de personagens RPG distribuindo 100 pontos entre 5 atributos diferentes (Força, Destreza, Inteligência, Vitalidade e Sorte), levando em consideração:

- Dano físico e mágico
- Pontos de vida (HP)
- Defesa
- Taxa de crítico
- Habilidades desbloqueadas
- Sinergia entre atributos

## 🧬 Funcionamento do Algoritmo Genético

### Cromossomo (Representação)
Cada indivíduo é representado por um vetor com 5 genes:
```
[Força, Destreza, Inteligência, Vitalidade, Sorte]
```

**Restrições:**
- Total de pontos = 100
- Máximo por atributo = 50
- Valores inteiros não negativos

### Função de Fitness
Avalia a eficiência em combate considerando:
- HP = 100 + (Vitalidade × 10)
- Dano Físico = (Força × 2) + (Destreza × 1.5)
- Dano Mágico = Inteligência × 2.5
- Taxa de Crítico = (Sorte + Destreza) / 200
- Defesa = (Vitalidade × 1.5) + (Força × 0.5)
- Bônus de Habilidades = Número de habilidades × 50
- Penalidade por desequilíbrio de atributos

### Operadores Genéticos

**Seleção:** Torneio com 3 competidores

**Cruzamento:** Blend Crossover (média ponderada)
- Filho = Pai1 × α + Pai2 × (1 - α)
- α é um valor aleatório entre 0 e 1

**Mutação:** Transferência de pontos entre atributos
- Taxa padrão: 15%
- Transfere de 1 a 10 pontos entre dois atributos aleatórios

**Substituição:** Elitismo (10%) + Substituição Geracional

## 🚀 Como Usar

### Pré-requisitos
- Navegador web moderno (Chrome, Firefox, Edge, Safari)

### Executar
1. Faça o download do arquivo `algoritmo_genetico_rpg.html`
2. Abra o arquivo em qualquer navegador
3. Configure os parâmetros (opcional):
   - Tamanho da População
   - Taxa de Mutação
   - Taxa de Elitismo
   - Delay entre gerações
4. Clique em "Iniciar Evolução"
5. Observe a evolução em tempo real!

## 📊 Visualizações

O projeto apresenta diversas visualizações em tempo real:

- **Melhor Build Atual:** Exibe os atributos, estatísticas e habilidades do melhor personagem
- **Gráfico de Evolução:** Mostra a evolução do fitness máximo e médio ao longo das gerações
- **Gráfico de Diversidade:** Monitora a diversidade genética da população
- **População Atual:** Grid com os 20 melhores indivíduos da geração atual
- **Log de Evolução:** Histórico de eventos e melhorias encontradas

## 🎮 Sistema de Habilidades

O personagem desbloqueia habilidades ao atingir requisitos mínimos de atributos:

| Habilidade | Requisitos |
|------------|------------|
| Golpe Poderoso | FOR ≥ 15 |
| Ataque Rápido | FOR ≥ 10, DEX ≥ 15 |
| Bola de Fogo | INT ≥ 20 |
| Escudo Arcano | DEX ≥ 5, INT ≥ 15 |
| Cura Divina | INT ≥ 25 |
| Fúria Berserker | FOR ≥ 25, DEX ≥ 10 |
| Esquiva Perfeita | FOR ≥ 5, DEX ≥ 25 |
| Raio Arcano | DEX ≥ 10, INT ≥ 30 |
| Contra-Ataque | FOR ≥ 15, DEX ≥ 20 |
| Invocação | FOR ≥ 5, DEX ≥ 5, INT ≥ 35 |

## 🛠️ Tecnologias Utilizadas

- HTML5
- CSS3
- JavaScript (Vanilla)
- Canvas API para gráficos

## 📈 Resultados Esperados

Após aproximadamente 80-100 gerações, o algoritmo converge para builds otimizadas que geralmente:
- Maximizam o número de habilidades desbloqueadas
- Equilibram dano e sobrevivência
- Apresentam boa sinergia entre atributos
- Atingem fitness 70-80% superior à população inicial aleatória

## 📝 Licença

Este projeto foi desenvolvido para fins acadêmicos.

## 🏫 Instituição

**Campus Cachoeiro de Itapemirim**
Curso: Sistemas de Informação
Disciplina: Técnicas de Programação Avançada
Professor: Rafael Vargas Mesquita
Ano: 2025
