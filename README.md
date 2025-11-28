# CICS-Multi-Screen-Terminal-Simulator

Uma ferramenta web gratuita que permite criar protótipos de telas 3270, navegar entre múltiplas telas, validar campos e exportar código BMS automaticamente — tudo sem precisar de um ambiente CICS real. Ideal para quem desenvolve em COBOL/CICS ou está começando no mundo mainframe.

**Link:**

[🖥️ CICS Multi-Screen Terminal Simulator](https://elainenunesm.github.io/CICS-Multi-Screen-Terminal-Simulator/)


**Informação para navegação no terminal:**

No terminal use a tecla tab.

# Resumo
Este artigo apresenta o CICS Screen Simulator, uma ferramenta web desenvolvida em HTML, CSS e JavaScript que permite a prototipação visual de telas de terminais 3270 (terminais do mainframe), simulação de navegação multi-screen e geração automática de código BMS (Basic Mapping Support). 

A ferramenta foi criada para atender desenvolvedores mainframe e estudantes que necessitam aprender ou prototipar interfaces CICS sem acesso a um ambiente real, reduzindo a curva de aprendizado e acelerando o ciclo de desenvolvimento.

## 1. Introdução
### 1.1 Contexto e Motivação
O CICS (Customer Information Control System) da IBM continua sendo uma das plataformas de processamento transacional mais utilizadas no mundo corporativo. Estima-se que 95% das transações de ATM e 80% das transações de cartão de crédito globais passem por sistemas CICS diariamente.

Apesar de sua importância crítica, o desenvolvimento e treinamento em CICS enfrenta desafios significativos:


| Desafio	 | Impacto  |
| --- | --- |
| Alto custo de licenciamento | Empresas pequenas e instituições de ensino têm acesso limitado |
| Complexidade de configuração | Semanas para provisionar ambiente de desenvolvimento |
| Escassez de profissionais | Média de idade dos programadores COBOL/CICS é 55+ anos |
| Ciclo de desenvolvimento lento | Impossível prototipar rapidamente sem ambiente completo |


### 1.2 Objetivo do Projeto
O CICS Screen Simulator foi desenvolvido com três objetivos principais:

**Prototipação Rápida:** 
Permitir a criação e visualização de telas CICS antes de escrever código

**Geração de Código:** 
Converter layouts de tela em código BMS válido automaticamente

**Treinamento:**
Oferecer ambiente de aprendizado para desenvolvedores iniciantes em mainframe

### 1.3 Diferenciais

| ABORDAGEM TRADICIONAL|
|  --- |
| Ideia → Escrever BMS → Compilar → Testar → Ajustar → Repetir |
| Tempo médio: 2-4 horas por tela    |

| COM CICS SCREEN SIMULATOR|
|  --- |
| Ideia → Prototipar Visual → Exportar BMS → Pronto!           |
|Tempo médio: 15-30 minutos por tela     |


## 2. Fundamentação Teórica
### 2.1 O Terminal 3270
O IBM 3270 é uma família de terminais de bloco que se comunica com mainframes através de um protocolo específico. 

Diferentemente de terminais de caractere, o 3270 transmite telas inteiras em blocos.

### Características principais:

**Dimensões padrão:**
24 linhas × 80 colunas (modelo 2) ou 27 × 132 (modelo 5)

**Campos:**
Áreas definidas para entrada ou exibição de dados

**Atributos:**
Controlam cor, intensidade, proteção e comportamento dos campos

**Teclas de função:**
PF1-PF24, PA1-PA3, Enter, Clear

### 2.2 Basic Mapping Support (BMS)

O BMS é a camada de mapeamento do CICS que separa a lógica de apresentação da lógica de negócio. Um mapa BMS define:


```bms
│  MAPSET (Conjunto de Mapas)                          
│  ├── MAP 1 (Tela individual)                         
│  │   ├── FIELD 1 (Campo: posição, tamanho, atrib.)   
│  │   ├── FIELD 2                                     
│  │   └── FIELD N                                     
│  ├── MAP 2                                           
│  └── MAP N  
```
## 3. Casos de Uso
### 3.1 Caso de Uso 1: Prototipação Rápida

**Cenário:**
Analista precisa validar layout de tela com usuário antes do desenvolvimento.

**FLUXO:**
1. Analista cria arquivo TXT com layout proposto
2. Importa no simulador
3. Ajusta posições e campos visualmente
4. Navega entre telas para demonstrar fluxo
5. Exporta para Excel para documentação
6. Usuário aprova layout
7. Exporta código BMS para desenvolvimento

**Economia de tempo estimada: 60-70%**

### 3.2 Caso de Uso 2: Treinamento de Desenvolvedores
**Cenário:** 
Empresa precisa treinar novos desenvolvedores em CICS/BMS.

**FLUXO:**
1. Instrutor prepara conjunto de telas de exemplo
2. Alunos importam e estudam estrutura
3. Alunos modificam campos e observam código BMS gerado
4. Exercício: criar tela do zero
5. Simulam navegação e validações
6. Comparam código gerado com padrões da empresa

**Benefício:**

Aprendizado sem necessidade de acesso a mainframe real.

### 3.3 Caso de Uso 3: Documentação de Sistema Legado
**Cenário:** 
Equipe precisa documentar sistema CICS existente para modernização.

**FLUXO:**
1. Importa layouts existentes (screenshot/transcrição)
2. Recria telas no simulador
3. Exporta para Excel com todas as definições
4. Gera documentação visual com tema claro
5. Usa como base para projeto de modernização

## 4. Funcionamento - Demonstração
### 4.1 Import TXT


```TXT

SISTEMA DE CADASTRO 
OPCAO: xxx












 
PF3=VOLTAR PF7=ANTERIOR PF8=PRÓXIMOPF12=AJUDA ENTER=DETALHAR 






 
 
```
* O txt precisa tem:
    *  24 linhas;
    *  80 bytes de colunas;
    *  A primeira linha em branco;
    *  E os campos de digitação minúsculo Alfa(zzz) númerico(xxx).

**No emulador CICS**

[🖥️ CICS Multi-Screen Terminal Simulator](https://elainenunesm.github.io/CICS-Multi-Screen-Terminal-Simulator/)

- Clicar no botão Carregar Telas TXT, importar 

![Carregar Telas TXT](https://github.com/user-attachments/assets/624c96e8-07da-4b9e-908b-f1161b9a420b "Carregar Telas TXT")

- No botão Carregar Telas TXT, importar

![Pós carregamento txt](https://github.com/user-attachments/assets/261f8efc-7d03-4a47-bf6e-445dde087645 "Pós carregamento txt")

- Tela carregou corretamente

![Carregamento da tela](https://github.com/user-attachments/assets/db68a321-9e09-466c-b7a5-61d7c4a75aeb "Carregamento da tela")

- Para mostrar no terminal outras telas carregadas só clicar com mouse, como no exemplo abaixo.

![carregar outras telas](https://github.com/user-attachments/assets/0b35482a-b9a0-4ea9-b6a5-4e737321118c "carregar outras telas")

- Configurar campos
Em Configuração de Validação de Campos (Opcional)
> Permite configurar teclas que validam campos

![Configurar campos](https://private-user-images.githubusercontent.com/9143866/519967309-f5760eed-7600-480c-a51d-453527413c93.jpg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjQzMDU3NDYsIm5iZiI6MTc2NDMwNTQ0NiwicGF0aCI6Ii85MTQzODY2LzUxOTk2NzMwOS1mNTc2MGVlZC03NjAwLTQ4MGMtYTUxZC00NTM1Mjc0MTNjOTMuanBnP1gtQW16LUFsZ29yaXRobT1BV1M0LUhNQUMtU0hBMjU2JlgtQW16LUNyZWRlbnRpYWw9QUtJQVZDT0RZTFNBNTNQUUs0WkElMkYyMDI1MTEyOCUyRnVzLWVhc3QtMSUyRnMzJTJGYXdzNF9yZXF1ZXN0JlgtQW16LURhdGU9MjAyNTExMjhUMDQ1MDQ2WiZYLUFtei1FeHBpcmVzPTMwMCZYLUFtei1TaWduYXR1cmU9NDk2Y2RjMzBmMjgzM2NhNTFjNjhhZWJlOGRlZTg3YmY0N2Y0NmJmM2FhZTA0ZDQ2MWI3NDE5YzRjZmVjM2M3ZiZYLUFtei1TaWduZWRIZWFkZXJzPWhvc3QifQ.PPlq5RK2kPjy1sdLr74xNy4Z0t4pYQGaAmNbd50fNkc "Configurar campos")

- Lado esquerdo ficam os campos da tela atual.

![Campos tela atual](https://github.com/user-attachments/assets/8ce3b1aa-fb37-4e9d-92e8-d58950e1a1b6 "Campos tela atual")

- Rolando mais a tela chega na opção atributos BMS.

![Atributos BMS](https://github.com/user-attachments/assets/80d2ff67-310e-4d88-a49c-60111d839af0 "Atributos BMS")

- Opção exportar BMS.

![Opção exportar BMS](https://github.com/user-attachments/assets/d7d867c6-fc96-4c25-bbf9-23e920b8aeb8 "Opção exportar BMS")

- Selecionar BMS.

![Opção BMS](https://github.com/user-attachments/assets/f08ffc32-bdba-4c87-a6bd-11728962d52d "Opção BMS")

- Código exportado.

```BMS
* ========================================
* BMS MAP DEFINITIONS
* Generated on XX/XX/XXXX, XX:XX:XX
* Total Screens: 1
* Label variables: NO (comments only)
* ========================================
TELAT  DFHMSD LANG=COBOL,                                              -
              MODE=INOUT,                                              -
              STORAGE=AUTO,                                            -
              TERM=3270,                                               -
              TIOAPFX=YES,                                             -
              TYPE=&&SYSPARM,                                          -
TELATM DFHMDI SIZE=(24,80),LINE=1,COLUMN=1                              
*      Screen: tela_teste
*
*      Field: MENSAGEM
MENSAG DFHMDF POS=(1,1),                                               -
              LENGTH=80,                                               -
              ATTRB=NORM                                                
       DFHMDF POS=(1,81),                                              -
              LENGTH=0,                                                -
              ATTRB=ASKIP                                               
        DFHMDF POS=(2,1),                                              -
              LENGTH=19,                                               -
              ATTRB=(ASKIP,NORM),                                      -
              INITIAL='SISTEMA DE CADASTRO'                             
        DFHMDF POS=(3,1),                                              -
              LENGTH=6,                                                -
              ATTRB=(ASKIP,NORM),                                      -
              INITIAL='OPCAO:'                                          
*      Field: OPCAO
OPCAOI DFHMDF POS=(3,8),                                               -
              LENGTH=3,                                                -
              ATTRB=(UNPROT,NUM,DRK,IC)                                 
       DFHMDF POS=(3,11),                                              -
              LENGTH=0,                                                -
              ATTRB=ASKIP                                               
*      REQUIRED FIELD
        DFHMDF POS=(17,1),                                             -
              LENGTH=45,                                               -
              ATTRB=(ASKIP,NORM),                                      -
              INITIAL='PF3=VOLTAR PF7=ANTERIOR PF8=PRÓXIMOPF12=AJUDA'   
        DFHMDF POS=(17,46),                                            -
              LENGTH=14,                                               -
              ATTRB=(ASKIP,NORM),                                      -
              INITIAL='ENTER=DETALHAR'                                  
       DFHMSD TYPE=FINAL                                                
       END                                                              

* ========================================
* VALIDATION KEYS CONFIGURATION
* Keys that trigger validation: ENTER
* ========================================

```

## 5. Demonstração Visual

### 4.1 Tela em Modo Dark (Mainframe)

- Tema dark que simula o mainframe.

![Tema dark simulador](https://github.com/user-attachments/assets/065eae88-8ed1-4a8b-9919-b51b21cb500b "Tema dark simulador")

- Terminal.

![Terminal](https://github.com/user-attachments/assets/189de18a-d2ef-4908-9e1b-41772303dae7 "Terminal")

  * Texto em verde sobre fundo preto
  * Fonte monoespaçada
  * Cursor piscante
  
  

## 5.2 Funcionalidades Implementadas vs em desenvolvimento
### Funcionalidade	Status	Observações

**Importar TXT**	
✅ Completo 
- Formato documentado

**Multi-screen (abas)**	
✅ Completo
- Até 10 telas simultâneas

**Navegação entre telas**	
✅ Completo	
- PF keys + opções de menu

**Validação de campos**	
✅ Básico 	
- Obrigatório, numérico, range

**Exportar BMS**	
✅ Completo	
- Código válido para compilação

**Exportar Excel**
✅ Completo	
- Definições e mapeamentos

**Tema Dark (Mainframe)**	
✅ Completo	
- Simula visualmente um terminal 3270

**Tema Claro**	
✅ Completo	
- Para quem não gosta da tela preta do mainframe

**Exporta copybook**	
✅ Completo	
- Precisa configurar os campos, realizar as validações para exportação correta.

### Funcionalidade em desenvolvimento

**Exportação**
As opções de exportação já estão funcionando, porém ainda apresentam alguns bugs e precisam de ajustes, especialmente nos formatos:

- JSON e COBOL

- Excel e CSV

### Observação

Embora a aplicação já esteja operando, ela ainda necessita de testes mais robustos e de correções adicionais. Mesmo assim, as funcionalidades principais — exportar BMS e simular navegação — já estão funcionando satisfatoriamente.

Atualmente, a interface ainda não é responsiva.

Este é apenas o primeiro artigo. Publicarei outros conteúdos explicando como utilizar a ferramenta para fins de estudo.

Obrigada!

> Palavras-chave: CICS, BMS, Mainframe, Simulador, Prototipação, 3270, Treinamento
