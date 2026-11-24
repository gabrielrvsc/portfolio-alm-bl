# portfolio-alm-bl

Modelo quantitativo didático e modular em **R** de **Asset-Liability Management (ALM) Pessoal** com **Surplus Black-Litterman** e otimização quadrática restrita (`quadprog`), comparando dois regimes profissionais (**Salário** vs. **Empreender**) na base monetária **BRL Real (descontado do IPCA)**.

## Arquitetura Planejada

```text
portfolio-alm-bl/
├── config/
│   └── assumptions.yaml          # Inputs de ativos, matriz de covariância, views BL, W_fin, C_bar e regimes
├── R/
│   ├── 00_utils.R                # Funções auxiliares e validação matricial
│   ├── 01_balanco_patrimonial.R  # Cálculo de H_0, L_0, Gap_k e razões h e l
│   ├── 02_black_litterman_base.R # Retornos implícitos Pi, mu_BL e Sigma_BL
│   ├── 03_alm_decomposicao.R     # Decomposição fechada (Tangente BL, Hedge H, Hedge L)
│   └── 04_otimizacao_restrita.R  # Otimização via quadprog com piso de liquidez e limites
├── reports/
│   └── fase1_bl_alm.Rmd          # Relatório didático em HTML (ggplot2 + knitr)
└── main.R                        # Pipeline sequencial (01 -> 04) e renderização do relatório
```

## Pré-requisitos de Ambiente

- **R** (>= 4.5)
- **Pandoc** (para renderização de RMarkdown em HTML)
- Pacotes R: `yaml`, `dplyr`, `tidyr`, `quadprog`, `ggplot2`, `knitr`, `rmarkdown`

## Status

- [x] Inicialização do projeto, ambiente R e repositório Git/GitHub
- [ ] Fase 1: Implementação dos módulos `config/`, `R/`, `reports/` e `main.R`
