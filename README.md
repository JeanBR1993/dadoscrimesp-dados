# Dados de Crimes São Paulo — dados abertos

Ocorrências criminais registradas por mês em cada delegacia da cidade de São Paulo desde 2002, com as áreas oficiais das delegacias, a população de cada área (Censo 2022) e indicadores dos últimos 12 meses. Organizado a partir das estatísticas mensais da Secretaria da Segurança Pública do Estado de São Paulo (SSP-SP).

Dados até **setembro de 2026**. Atualizado todo mês, quando a SSP publica um mês novo.
Site: https://dadoscrimesp.com.br · Metodologia: https://dadoscrimesp.com.br/metodologia/

## Arquivos

| Arquivo | Conteúdo |
|---|---|
| `ocorrencias_mensais.csv.gz` | Casos por mês, delegacia e categoria da SSP, de jan/2002 até o último mês publicado (formato longo). |
| `delegacias.csv` | As 94 delegacias da capital: nome, nome oficial na SSP, endereço, coordenadas, zona, moradores (Censo 2022), distritos e página no site. |
| `delegacias.geojson` | Áreas oficiais das delegacias (GeoSampa/SSP), simplificadas em ~11 m. |
| `indicadores_12_meses.csv` | Roubos, furtos, mortes violentas (cvli) e estupros dos últimos 12 meses, com taxas por 100 mil moradores e o índice ponderado do site. |
| `distritos_delegacias.csv` | Ligação entre delegacias e os 96 distritos, pelos moradores dos setores censitários. |

## Antes de somar: categorias que se sobrepõem

A SSP publica totais junto com as partes que os compõem e mistura ocorrências com vítimas.
Somar todas as categorias conta a mesma ocorrência duas vezes.

Partes que já estão dentro de um total:
- `HOMICÍDIO DOLOSO POR ACIDENTE DE TRÂNSITO` já está dentro de `HOMICÍDIO DOLOSO (2)`
- `Nº DE VÍTIMAS EM HOMICÍDIO DOLOSO POR ACIDENTE DE TRÂNSITO` já está dentro de `Nº DE VÍTIMAS EM HOMICÍDIO DOLOSO (3)`
- `ESTUPRO` já está dentro de `TOTAL DE ESTUPRO (4)`
- `ESTUPRO DE VULNERÁVEL` já está dentro de `TOTAL DE ESTUPRO (4)`
- `ROUBO - OUTROS` já está dentro de `TOTAL DE ROUBO - OUTROS (1)`
- `ROUBO DE CARGA` já está dentro de `TOTAL DE ROUBO - OUTROS (1)`
- `ROUBO A BANCO` já está dentro de `TOTAL DE ROUBO - OUTROS (1)`

Categorias que contam vítimas, não ocorrências:
- `Nº DE VÍTIMAS EM HOMICÍDIO DOLOSO (3)`
- `Nº DE VÍTIMAS EM HOMICÍDIO DOLOSO POR ACIDENTE DE TRÂNSITO`
- `Nº DE VÍTIMAS EM LATROCÍNIO`

Outras quebras de série: a Lei 12.015 (agosto de 2009) ampliou a definição de estupro; as partes dos totais de
estupro e de roubo só aparecem de forma completa a partir de 2017 (com registros esparsos em 2015 e 2016); 2020 foi
afetado pela pandemia. São registros de boletins de ocorrência, não todos os crimes que acontecem.

## Fontes e licença

- Ocorrências: Secretaria da Segurança Pública do Estado de São Paulo (SSP-SP), estatísticas mensais por delegacia.
- Áreas das delegacias e distritos: GeoSampa, Prefeitura de São Paulo (CC BY-SA 4.0).
- População: IBGE, Censo Demográfico 2022, agregados por setor censitário.

Os dados derivados deste pacote estão sob a licença [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.pt-br).
Projeto independente, sem vínculo com a SSP-SP.

## Como citar

Dados de Crimes São Paulo. *Ocorrências criminais por delegacia na cidade de São Paulo, 2002–2026*.
Dados até setembro de 2026. Disponível em: https://dadoscrimesp.com.br/dados/
