# Trabalho-3-IA
Trabalho 3 da matéria de IA da UFAM

#EQUIPE: Beatriz Emily Silva Aguiar
> matrícula: 22154303

> Turma: CB02

## 1. Neuro-Symbolic AI (NeSy) e Logic Tensor Networks (LTN)

### Neuro-Symbolic Artificial Intelligence (NeSy)

A Inteligência Artificial Neuro-Simbólica (NeSy) combina dois paradigmas tradicionais da Inteligência Artificial:  
(i) **modelos neurais**, responsáveis por aprender padrões a partir de dados contínuos e possivelmente ruidosos, e  
(ii) **representações simbólicas**, responsáveis por expressar conhecimento explícito por meio de regras e axiomas lógicos.

No contexto deste trabalho, essa integração pode ser observada na forma como predicados neurais são utilizados para identificar atributos e relações espaciais entre objetos a partir de suas *features*. Por exemplo, predicados parametrizados por redes neurais foram capazes de inferir o posicionamento relativo entre dois objetos (como esquerda/direita ou acima/abaixo) a partir das coordenadas espaciais.

Além disso, o modelo inclui **parâmetros treináveis guiados por restrições lógicas**, em vez de rótulos diretos. 

**Um exemplo disso** é o uso de axiomas envolvendo proximidade espacial. A partir da regra lógica *“se dois objetos são triângulos e possuem o mesmo tamanho, então eles são considerados próximos”*, o parâmetro que define a noção de distância foi ajustado durante o treinamento para satisfazer essa restrição.

Esse tipo de formulação evidencia o poder dos axiomas no paradigma neuro-simbólico, pois eles não apenas impõem consistência ao modelo, mas também orientam o aprendizado de parâmetros contínuos de forma indireta, permitindo que o sistema aprenda conceitos sem supervisão explícita.



---

### Logic Tensor Networks (LTN)

Logic Tensor Networks (LTN) são um framework neuro-simbólico que integra **Lógica de Primeira Ordem (First-Order Logic)** com **redes neurais diferenciáveis**. Em LTN, predicados lógicos são parametrizados por modelos neurais (por exemplo, MLPs), que produzem valores de verdade contínuos no intervalo \([0,1]\).

As fórmulas lógicas são convertidas em funções diferenciáveis por meio de **fuzzy logic**, permitindo que a satisfação das regras seja otimizada via **gradiente descendente**. Dessa forma, o treinamento busca maximizar a **satisfatibilidade global (SAT)** de um conjunto de axiomas, ao mesmo tempo em que ajusta os parâmetros neurais dos predicados.

No contexto deste trabalho, o LTN é utilizado para modelar atributos absolutos (como forma, cor e tamanho) e relações espaciais (como esquerda/direita, acima/abaixo e proximidade), garantindo que o aprendizado respeite restrições lógicas como exclusividade, transitividade, inversos e regras de empilhamento.

Essa abordagem permite um raciocínio mais estruturado e interpretável, indo além de classificações isoladas e incorporando conhecimento simbólico ao processo de aprendizagem.

---
***IMPORTANTE***  
Este trabalho foi desenvolvido em duas etapas. Inicialmente, foram implementados **modelos determinísticos**, com foco principal na definição e validação dos **axiomas lógicos** e das regras de raciocínio espacial. Somente após essa etapa os **modelos neurais (MLP)** foram introduzidos para parametrizar os predicados.

Essa abordagem permitiu uma comparação direta entre um **modelo puramente determinístico**, baseado em regras explícitas, e um **modelo neuro-simbólico**, no qual os predicados são aprendidos a partir dos dados, mantendo as mesmas restrições lógicas. Dessa forma, foi possível avaliar o impacto do aprendizado neural sem alterar a estrutura lógica do sistema.



