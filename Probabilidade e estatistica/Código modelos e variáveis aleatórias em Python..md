
```
Código (Python) de Probabilidade e Estatística modelos e variáveis aleatórias:

import random
import matplotlib.pyplot as plt

n = 1000

# Modelo 1 - Uniforme
uniforme = [random.random() for _ in range(n)]

# Modelo 2 - Bernoulli
bernoulli = [random.randint(0,1) for _ in range(n)]

# Modelo 3 - Discreto (1,2,3 com probabilidades diferentes)
discreto = []
for _ in range(n):
    r = random.random()
    if r < 0.5:
        discreto.append(1)
    elif r < 0.8:
        discreto.append(2)
    else:
        discreto.append(3)

# ---- GRÁFICOS ----

plt.figure(figsize=(15,4))

plt.subplot(1,3,1)
plt.hist(uniforme, bins=20)
plt.title("Distribuição Uniforme")

plt.subplot(1,3,2)
plt.hist(bernoulli, bins=2)
plt.title("Distribuição Bernoulli")

plt.subplot(1,3,3)
plt.hist(discreto, bins=3)
plt.title("Distribuição Discreta")

plt.show()
```