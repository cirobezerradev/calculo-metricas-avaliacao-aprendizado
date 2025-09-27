# Desafio de Cálculo de Métricas de Avaliação de Aprendizado - BootCamp Machine Learning Dio.me

Neste projeto, vamos calcular as principais métricas para avaliação de modelos de
classificação de dados, como acurácia, sensibilidade (recall), especificidade, precisão
e F-score. Para que seja possível implementar estas funções, você deve utilizar os
métodos e suas fórmulas correspondentes (Tabela 1).

Para a leitura dos valores de VP, VN, FP e FN, será necessário escolher uma matriz
de confusão para a base dos cálculos. Essa matriz você pode escolher de forma
arbitraria, pois nosso objetivo é entender como funciona cada métrica. 

Escolhi um exemplo aleatório de uma matriz de filtro de SPAM

## Matriz de Confusão — Filtro de SPAM

<table>
  <tr>
    <th rowspan="2" colspan="2">Matriz de Confusão</th>
    <th colspan="2">Valores de Previsão</th>
  </tr>
  <tr>
    <th>SPAM</th>
    <th>NÃO SPAM</th>
  </tr>
  <tr>
    <td rowspan="2"><b>Valor Real</b></td>
    <td><b>SPAM</b></td>
    <td>VP = 80 🟩</td>
    <td>FN = 10 🟥</td>
  </tr>
  <tr>
    <td><b>NÃO SPAM</b></td>
    <td>FP = 20 🟥</td>
    <td>VN = 90 🟩</td>
  </tr>
</table>

---
## Cálculo de Métricas

### Sensibilidade (Recall)
Mede a proporção de casos positivos reais que foram corretamente identificados pelo modelo.
<br><img width="214" height="40" alt="sensibilidade" src="https://github.com/user-attachments/assets/3827fe8b-2166-4078-ac97-04278f9d6757" /><br>
**Logo:** 
<br> Sensibilidade = 80 / (80 + 10) ≅ 0,88 ou ≅ 88%
> No treinamento de modelos de Machine Learning aplicados a diagnósticos médicos, costuma-se priorizar alta sensibilidade, porque errar para o lado do falso negativo (não diagnosticar alguém doente) é muito mais grave do que gerar um falso positivo (diagnosticar alguém saudável como doente).

---
### Especificidade
Mede a proporção de casos negativos reais que foram corretamente identificados pelo modelo.
<br><img width="228" height="40" alt="especif" src="https://github.com/user-attachments/assets/b1e0e3bf-2455-4782-a4e4-31a3329a8d05" /><br>
**Logo:**
<br> Especificidade = 90 /(90 + 20) ≅ 0,81 ou ≅ 81%
> No caso do Filtro de Spam, se a métrica de especificide for baixa, haverá muito alerta falso de Spam, isso ocorre quando a taxa de FP está alta. Portanto o ideal é termos uma métrica especificidade alta pois evita alarme falso de spam.

---
### Acurácia (Accuracy)
Mede a proporção total de previsões corretas (tanto positivas quanto negativas) em relação ao número total de casos.
<br><img width="282" height="40" alt="acuracia" src="https://github.com/user-attachments/assets/8ea62f06-5521-43fa-b7d2-ebd1a96e8d1a" /><br>
**Logo:**
<br> Acuracia = (80 + 90) / (80 + 90 + 10 + 20) = 170 / 200 = 0,85 ou = 85%
> Devemos tomar cuidado em considerar essa métrica quando usamos dados desbalanceados
---
### Precisão (Precision)
Mede a proporção de previsões positivas que foram realmente corretas.
<br><img width="176" height="40" alt="precisao" src="https://github.com/user-attachments/assets/17dc8b6a-74d2-4f43-9333-50a85d0e2d08" /><br>
**Logo:**
<br> Precisao = 80 / (80+20) = 0,8 ou 80%

---
### F-score (F1-score)
É a média harmônica da precisão e da sensibilidade.
<br><img width="331" height="40" alt="fscore" src="https://github.com/user-attachments/assets/d708be61-437e-4eb9-81e0-cbbd0d2027d5" /><br>
**Logo:**
<br> F-score = 2 * (Precisao * Sensibilidade) / (Precisao + Sensibilidade) = 2 * 0,704 / 1,68 ≅ 0,83 ou ≅ 83% <br>
> F-Score é particularmente útil em conjuntos de dados desbalanceados, onde a acurácia pode não ser uma boa medida de desempenho, ou seja, um alto F-score indica que tanto tem uma alta precisão quanto uma alta sensibilidadde.




