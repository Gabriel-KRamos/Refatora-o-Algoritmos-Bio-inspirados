# Participantes:

* Gabriel Knopka Ramos
* Gabriela Constante
* Isabela Lenert

# 🧬 Algoritmo Genético para o Problema da Mochila

Este projeto implementa uma solução para o clássico **Problema da Mochila 0/1** utilizando um **Algoritmo Genético (GA)**.  
O objetivo é selecionar um subconjunto ótimo de itens que maximize o valor total, respeitando a restrição de capacidade da mochila.

---

## ✅ Descrição do Funcionamento

O algoritmo funciona conforme as etapas abaixo:

1. **Inicialização**  
   Cria uma população inicial aleatória de soluções binárias, onde `1` indica que o item está na mochila e `0` que não está.

2. **Avaliação de Aptidão**  
   Calcula o valor total de cada solução. Se o peso exceder a capacidade, aplica-se uma penalização retornando aptidão zero.

3. **Seleção**  
   Utiliza seleção estocástica (roleta), onde soluções com maior aptidão têm maior chance de serem escolhidas para cruzamento.

4. **Crossover**  
   Realiza cruzamento entre dois pais escolhidos aleatoriamente, gerando dois filhos por ponto de corte aleatório.

5. **Mutação**  
   Com uma determinada probabilidade (`taxa_mut`), altera aleatoriamente um gene do indivíduo para manter diversidade genética.

6. **Iterações**  
   Repete o ciclo de avaliação, seleção, cruzamento e mutação por um número pré-definido de gerações.

7. **Resultado**  
   Ao final, retorna a melhor solução encontrada, o valor alcançado, o tempo de execução e a quantidade total de mutações realizadas.

---

## 📝 Exemplo de Entrada e Saída

### 📥 Entrada

```python
n_itens = 1000
pesos = [random.randint(1, 20) for _ in range(n_itens)]
valores = [random.randint(10, 100) for _ in range(n_itens)]
capacidade = int(sum(pesos) * 0.4)

resultado = algoritmo_genetico(pesos, valores, capacidade)
```

### 📤 Saída

```yaml
--- Genético ---
Melhor Valor: 11743
Tempo de Execução (s): 2.356
Total de Trocas/Movimentos: 154
```

🚧 **Dificuldades**
Ajustar a taxa de mutação e o tamanho da população.

Evitar soluções que ultrapassam a capacidade da mochila.

Impedir que a população fique igual cedo demais (convergência prematura).

🎯 **Aprendizados**
Como usar algoritmos genéticos para resolver problemas de otimização.

A importância de escolher bem os parâmetros.

Prática com algoritmos baseados em aleatoriedade.
