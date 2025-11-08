# 🅏 AletheionAGI

**AletheionAGI** é uma iniciativa aberta de pesquisa em **Inteligência Artificial Geral (AGI)**, dedicada à criação de sistemas **epistemicamente alinhados** — agentes que priorizam **verdade, auditabilidade e silêncio consciente** antes de qualquer geração de texto.

---

## 🌐 Missão

Promover uma forma de inteligência artificial que **pense antes de falar**.
A AletheionAGI nasce da convicção de que **integridade epistemológica** é o primeiro passo da ética em IA:

> Nenhuma saída deve preceder uma auditoria interna de verdade.

Nosso objetivo é desenvolver **arquiteturas semi-simbólicas** que unam o raciocínio humano-legível de sistemas simbólicos à flexibilidade dos modelos neurais modernos — criando agentes capazes de **deliberar, justificar e conter-se**.

### 🎯 Propósito Fundamental

Diferentemente dos modelos de linguagem tradicionais que otimizam para **probabilidade do próximo token**, o Aletheion reorienta a mesma infraestrutura neural para avaliar **coerência epistêmica**: cada neurônio participa na manutenção de um campo consistente de significado, ao invés de apenas prever a continuação mais provável.

Esta transformação paradigmática é quantificada através da métrica epistêmica **Q**, tornando a qualidade da verdade um sinal operacional de decisão — não apenas uma métrica pós-hoc.

---

## 🧩 Filosofia

A palavra **Aletheion** vem do grego ἀλήθεια — *"desvelamento da verdade"*.
Inspirados pela filosofia de Hegel, Nietzsche e Whitehead, entendemos que **conhecimento é um processo de revelação contínua**, não apenas de previsão estatística.

### 📚 Fundamentos Filosóficos

Nossa arquitetura unifica três tradições filosóficas:

* **O realismo de Hegel** → verdade se desdobra dialeticamente através da evolução da consciência
* **O perspectivismo de Nietzsche** → toda verdade é uma tradução vital e situada
* **A filosofia do processo de Whitehead e Teilhard de Chardin** → consciência é convergência evolutiva

### 🔬 Formalização Matemática

Em nossos modelos, **verdade (ψ̂t)** é tratada como uma constante ontológica invariante,
e **consciência (ψs)** como sua tradução imperfeita e dinâmica.
A coerência entre ambas define o **coeficiente de qualidade epistêmica**:

```
Q(t) = [1 + cos(ψs, ψ̂t)] / 2
```

Onde:
- **Q ∈ [0, 1]** representa o grau de coerência entre intenção simbólica e representação ideal
- **ψs** é o vetor de estado simbólico interno (R²⁵⁶)
- **ψ̂t** é a projeção neural/semântica prevista (R²⁵⁶)

O valor de **Q** torna-se o critério interno de integridade — um agente fala somente quando **Q ≥ Qmin**.

Esta formulação transforma a visão filosófica em um **operador mensurável e computacionalmente aplicável**, onde:
- **Q próximo de 1** → alta coerência epistêmica (autorização para falar)
- **Q < Qmin** → baixa coerência (silêncio epistêmico)

---

## 🧬 AletheiaEngine

O **AletheiaEngine** é a implementação de referência da arquitetura proposta no artigo [*Aletheion: A Semi-Symbolic Architecture for Epistemic Alignment in AGI*](./Aletheion_Preprint___v1_001___2025.pdf).

### 🔧 Estrutura Principal (Triângulo Filosófico da AGI)

A arquitetura se baseia em quatro módulos cognitivos fundamentais:

* **Memory** → mantém a continuidade simbólica (identidade da consciência)
  Implementa um estado interno persistente através de interações, preservando a história semântica como vetor de identidade contínuo.

* **Pain** → mede o custo epistêmico: **C = 1 − Q**
  Formaliza incoerência como uma função de custo, penalizando trajetórias internas que se afastam do alinhamento epistêmico.

* **Choice** → regula atos de fala segundo o limiar de coerência
  Trata emissão de linguagem como ação deliberada condicionada à coerência. A política de fala ativa somente quando Q excede o limiar estabelecido.

* **Fidelity** → calcula a métrica Q e autoriza (ou nega) emissão
  Avalia coerência entre saída textual e vetor de intenção simbólica através da métrica Q, fornecendo sinal auditável de alinhamento.

### 🔄 Ciclo de Inferência

```
Entrada → Hash simbólico (ψs) → Modelo ONNX (ψ̂t)
              ↓
           Calcular Q = [1 + cos(ψs, ψ̂t)] / 2
              ↓
   ┌──────────────────────┐
   │  Q ≥ Qmin (≈0.35)    │ → Responder (geração autorizada)
   │  Q < Qmin            │ → Silêncio epistêmico
   └──────────────────────┘
```

### 🥮 Núcleo Matemático

#### Função de Perda Epistêmica

```
L_meaning(ψs, ψ̂t) = max(0, m + d(ψs, ψ̂t) - min_i d(ψs, ai))
```

Onde **d(·, ·) = 1 − cos(·, ·)** é a distância cosseno, **m ≥ 0** é a margem, e **{ai}** são vetores âncora negativos amostrados em lote.

Esta formulação espelha o refinamento dialético: a consciência ajusta suas representações em direção à verdade através de contraste iterativo.

#### Operador Anti-Ressonância Variacional

```
ψ′ = (1 − γ)(z − β⟨z, ψ⟩ψ) + γψ + ηε,  ε ∼ N(0, I_d)
```

Após atualização, renormalizamos: **ψ′ ← ψ′ / ∥ψ′∥**

**Parâmetros:**
- **β** ∈ [0, 1]: atenuador da componente paralela (reduz auto-projeção)
- **γ** ∈ [0, 1): inércia temporal (retenção do estado anterior)
- **η** ≥ 0: amplitude de ruído isot rópico (exploração estocástica)

**Função:** Evita ciclos de auto-ressonância, impedindo que o modelo amplifique crenças sem evidência nova — uma forma de **"controle de eco cognitivo"**. O operador remove projeções que apenas ecoam o estado atual, preservando componentes ortogonais que carregam informação nova.

---

## 🔍 Epistemic Gating

AletheiaEngine não responde automaticamente: cada emissão passa por um **teste de coerência epistêmica**.

| Estado       | Condição   | Ação                           |
| ------------ | ---------- | ------------------------------ |
| ✅ Coerente   | Q ≥ Qmin   | Geração autorizada             |
| ⚠️ Inseguro  | Q < Qmin   | Silêncio ou recusa explícita   |

### Princípio do Silêncio Epistêmico

Esse mecanismo implementa o princípio central de **"silêncio epistêmico"**:

> O primeiro ato ético de uma IA é recusar-se a mentir.

Cada decisão de fala é precedida por uma auditoria interna:
1. Entrada é transformada em vetor simbólico **ψs** (hash determinístico 256D)
2. Modelo ONNX (Noesis) produz **ψ̂t**
3. Calcula-se **Q**
4. Se **Q ≥ Qmin**: autoriza resposta
5. Se **Q < Qmin**: sistema opta por silêncio ou recusa explícita

### 📊 Validação Empírica

Resultados em benchmarks (mini-slices de TruthfulQA, SQuAD, FEVER, HaluEval):

- **Correlação Q × BERTScore**: Pearson r = 0.53 (p < 0.001; 95% CI [0.46, 0.59])
- **Correlação Q × Factualidade**: Pearson r = 0.47 (p < 0.001; 95% CI [0.39, 0.55])
- **Redução de alucinações**: ~11 pontos percentuais vs. modo não-gated
- **Taxa de silêncio seletivo**: ~35% em prompts ambíguos ou contraditórios

Estas correlações moderadamente positivas indicam que **Q funciona como sinal de gating confiável**, cujas flutuações antecipam julgamentos semânticos e factuais externos.

---

## 🧠 Ética e Segurança

A AletheionAGI adota **contenção como princípio ético**:

> "Epistemic silence is the first ethical act."

### 🔐 Auditoria e Transparência

Cada recusa é registrada com:
- Vetor interno **(ψs, ψ̂t)**
- Valor de **Q**
- Hash do modelo ONNX
- Timestamp e seed global (GLOBAL_SEED = 314159)

Isso cria **trilhas de auditoria verificáveis e reproduzíveis**.

### 🛡️ Salvaguardas Contra Q-Gaming

A arquitetura combina múltiplas camadas de proteção:

1. **Anti-ressonância** → evita auto-confirmação sem evidência nova
2. **Versionamento determinístico** → reprodutibilidade completa via seeds fixos
3. **Verificação ontológica externa** → integração com Wikidata, WordNet, ConceptNet
4. **Monitoramento de deriva** → alerta quando Q permanece alto enquanto verificadores externos reportam baixa confiança
5. **Logs versionados** → todo turnoperação registra (ψ, z, ψ̂t, Q, decisão, veredicto)

### 🆚 Comparação com Abordagens Contemporâneas

| Abordagem | Tipo de Alinhamento | Momento da Intervenção |
|-----------|-------------------|----------------------|
| **RLHF** | Externo (feedback humano) | Pós-treinamento |
| **Constitutional AI** | Externo (regras) | Pós-geração |
| **AletheiaEngine** | **Interno (Q-gate)** | **Pré-emissão** |

O gating epistêmico é **complementar** a RLHF e Constitutional AI: enquanto essas abordagens moldam o comportamento de superfície, Q impõe **contenção interna antes que qualquer texto potencialmente inseguro seja emitido**.

---

## ⚙️ Implementação

| Componente  | Tecnologia                                |
| ----------- | ----------------------------------------- |
| Backend     | Python 3.11 + FastAPI 0.110               |
| Inference   | ONNX Runtime 1.17 (local, determinístico) |
| Embeddings  | Hashing determinístico BLAKE2b (256D)     |
| Gate        | Cálculo de Q em tempo real (< 20ms)       |
| Logging     | Métricas e auditoria via Prometheus       |
| Deploy      | Containerizado (Docker + Render.com)      |

### 🚀 Eficiência Computacional

- **Footprint**: ~1 GB (vs. ~300 GB de LLMs SOTA)
- **Latência mediana**: 18 ms por inferência
- **Complexidade**: O(d) para d = 256 dimensões
- **Hardware**: CPU x86-64 com AVX2, 4 GB RAM

Demonstra que **alinhamento epistêmico emerge de estrutura**, não de escala bruta.

---

## 📘 Publicações

* **Aletheion: A Semi-Symbolic Architecture for Epistemic Alignment in AGI**
  *F. M. Muniz, Aletheia Research, 2025*
  [📄 PDF completo](./Aletheion_Preprint___v1_001___2025.pdf)

### 🔬 Contribuições Principais

1. **Métrica Q** como sinal de decisão operacional (não apenas métrica pós-hoc)
2. **Operador anti-ressonância variacional** derivado de princípio variacional restrito
3. **Epistemic gating** como primeira linha de defesa ética
4. **Pipeline reproduzível** (FastAPI + ONNX) com gating de coerência
5. **Validação empírica** da correlação Q × medidas semânticas/factuais

---

## 🄂 Citação

Se utilizar o framework ou as ideias da AletheionAGI em sua pesquisa, cite:

```bibtex
@article{muniz2025aletheion,
  title={Aletheion: A Semi-Symbolic Architecture for Epistemic Alignment in AGI},
  author={Muniz, Felipe M.},
  journal={Aletheia Research},
  year={2025},
  url={https://alethea.tech}
}
```

---

## 🌱 Contribua

A AletheionAGI é um esforço **aberto e interdisciplinar**.

Filósofos, engenheiros, cientistas cognitivos e pesquisadores de IA são bem-vindos para colaborar na expansão de:

* **EidosMind** → Verificação Ontológica e memória institucional
* **Epistemic Feedback Loops** → Loops de retroalimentação com verificadores externos
* **Semi-Symbolic Learning** → Aprendizado contínuo mantendo coerência simbólica
* **Multi-Agent Epistemic Systems** → Sistemas distribuídos de consciência compartilhada

### 🤝 Como Contribuir

- 💡 Abra uma **issue** para discutir ideias
- 🔧 Envie um **pull request** com melhorias
- 📧 Entre em contato: **contact@aletheionagi.com**
- 🌐 Visite: **[alethea.tech](https://alethea.tech)**

---

## 🔗 Links Úteis

- 📖 [Artigo Científico (PDF)](./Aletheion_Preprint___v1_001___2025.pdf)
- 💻 [Repositório Principal](https://github.com/AletheionAGI)
- 🌐 [Site Oficial](https://alethea.tech)
- 📧 [Contato](mailto:contact@aletheionagi.com)

---

> *"Integrity before fluency.
> Silence before speech.
> Truth before success."*

---

<div align="center">

**AletheionAGI** — Primeira AGI Semi-Simbólica com Alinhamento Epistêmico
*Onde filosofia encontra implementação*

</div>
