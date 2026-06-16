# Análise Comparativa de Clusters de Genes Biossintéticos (BGCs) no Gênero *Pleurotus*

Este repositório contém o pipeline de dados e os scripts de visualização avançada desenvolvidos para a análise comparativa de **Clusters de Genes Biossintéticos (BGCs)** e **Famílias de Clusters Gênicos (GCFs)** entre espécies de fungos do gênero *Pleurotus* (cogumelos ostra). 

Este trabalho integra as frentes de bioinformática e ciência de dados da pesquisa: *"Comparative Analysis of Biosynthetic Gene Clusters and In Silico Characterization of Polyketide Synthases in Pleurotus Species"*.

---

## 🧬 Contexto Científico da Pesquisa

Os cogumelos do gênero *Pleurotus* possuem imensa importância econômica, nutricional e biotecnológica. Eles são fungos saprótrofos eficientes na degradação de lignina e madeira, além de serem reconhecidos como produtores de uma vasta gama de metabólitos secundários bioativos com propriedades medicinais (antibióticos, antifúngicos e antivirais).

Apesar de sua relevância mundial, os recursos genômicos anotados para o gênero historicamente permaneceram escassos. Esta pesquisa expande essa fronteira através de:
1. **Sequenciamento de Nova Geração (NGS)**: Sequenciamento, montagem e anotação do genoma da linhagem monocariótica ***Pleurotus albidus* MPD161** (via tecnologia *Oxford Nanopore MinION*), alcançando um genoma de 40.54 Mb e predizendo 14.015 genes funcionais.
2. **Genômica Comparativa**: Análise evolutiva e metabólica cruzada englobando **9 espécies chave** do gênero: *P. albidus*, *P. pulmonarius*, *P. ostreatus*, *P. eryngii*, *P. cornucopiae*, *P. djamor*, *P. placentodes* e *P. cystidiosus*.
3. **Mapeamento do Metabolismo Secundário**: Predição de rotas biossintéticas ocultas (como Terpenos, NRPS e Sintases de Policetídeos - PKS Tipo I) utilizando a plataforma **antiSMASH**.

---

## 📊 O Papel deste Repositório e do Gráfico UpSet

Para compreender como o potencial biossintético é compartilhado evolutivamente entre as 9 espécies, os BGCs preditos pelo antiSMASH foram agrupados em **Famílias de Clusters Gênicos (GCFs)** por similaridade ortóloga. 

O script contido neste repositório gera um **Gráfico UpSet Empilhado (Stacked UpSet Chart)** customizado para mapear essas interseções metabólicas:

* **O Gráfico de Interseção (Topo)**: Mede o compartilhamento científico de **GCFs** (Famílias). Ele agrupa os clusters para revelar quais vias metabólicas são altamente conservadas no "core genômico" do gênero e quais são exclusividades linhagem-específicas (exoluções biossintéticas de espécies isoladas).
* **As Barras Empilhadas (Cores)**: Categorizam as famílias de acordo com a classe química do metabólito predito (Terpenes, NRPS, NRPS-like, Polyketides/PKS, etc.).
* **A Legenda de Totais (Esquerda - Ajuste Técnico)**: Exibe a contagem **bruta e real de BGCs individuais (linhas do CSV original)** presentes no banco de dados de cada espécie (ex: exibindo o valor exato de 70 para *P. djamor* e 42 para *P. albidus*), garantindo a integridade quantitativa dos dados biológicos sem distorcer o visual das interseções.

---

## 📈 Visualização dos Resultados


O gráfico final gerado pelo pipeline correlaciona visualmente as classes de BGCs e o perfil de distribuição genômica:

![Distribuição de Famílias Biossintéticas e Interseções entre Espécies](grafico_final_com_legenda.png)

---

## 🛠️ Instalação e Requisitos

Para executar o notebook ou script localmente, certifique-se de ter o Python 3.x instalado com as seguintes dependências de Sistemas de Informação/Ciência de Dados:

    Baixe os arquivos deste repositório.

    Certifique-se de manter o arquivo de dados brutos (no nosso caso foi um .csv) no mesmo diretório do arquivo de código.

    Execute o Notebook ou rode o script Python diretamente:
    Bash

    python Stacked_Bar_Upset_Chart.py

O script gerará automaticamente os arquivos de saída de alta resolução: grafico_final.svg (formato vetorial ideal para publicação científica) e grafico_final_com_legenda.png (ideal para apresentações).

