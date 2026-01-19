# Formulário de Convite - Portfólio

Um formulário elegante e responsivo para criação de convites digitais, desenvolvido com HTML5 e CSS3 puro. O projeto demonstra técnicas avançadas de CSS, validação de formulários sem JavaScript e sistema de temas personalizáveis.

## 🎯 Características

- ✨ Design moderno e responsivo
- 🎨 Sistema de tema claro/escuro com toggle
- 📱 Totalmente responsivo em todos os dispositivos
- ✅ Validação de formulário com CSS puro (sem JavaScript)
- 🎪 Seletor de cores personalizado com 11 opções
- 🎭 Seleção de tema do evento (Aniversário, Casamento, Natal, etc.)
- 📅 Campos de data e hora integrados
- ☑️ Checkboxes customizados com animação
- 🔴 Mensagens de erro em tempo real (CSS-only)
- 🖼️ Sistema de upload de imagem
- 💅 Estilo claro/escuro para convites

## 🚀 Como Executar

### Pré-requisitos

- Navegador web moderno (Chrome 105+, Firefox 121+, Safari 15.4+, Edge 105+)
- Suporte ao seletor CSS `:has()` (disponível em navegadores modernos)

### Método 1: Abrir Arquivo Diretamente

1. Navegue até a pasta do projeto:

   ```
   c:\Users\lmp-8\Documents\CursoRocketSeat\FormDeConvite
   ```

2. Clique duas vezes no arquivo `index.html` para abrir no navegador padrão

### Método 2: Usar um Servidor Local (Recomendado)

#### Com Python 3:

```bash
cd c:\Users\lmp-8\Documents\CursoRocketSeat\FormDeConvite
python -m http.server 8000
```

Acesse: `http://localhost:8000`

#### Com Node.js (http-server):

```bash
npx http-server
```

Acesse: `http://localhost:8080`

#### Com Live Server (VS Code):

1. Instale a extensão "Live Server" no VS Code
2. Clique com botão direito em `index.html`
3. Selecione "Open with Live Server"

## 📂 Estrutura do Projeto

```
FormDeConvite/
├── index.html                    # Estrutura HTML do formulário
├── README.md                     # Documentação do projeto
├── Background.png                # Imagem de fundo do aside
├── Logo.svg                      # Logo do projeto
├── assets/
│   ├── icons/                    # Ícones SVG
│   │   ├── calendar.svg          # Ícone de calendário
│   │   ├── contact.svg           # Ícone de contato
│   │   ├── paintbrush-vertical.svg # Ícone de personalização
│   │   ├── check.svg             # Ícone de check
│   │   ├── circle-alert.svg      # Ícone de erro
│   │   ├── building-2.svg        # Ícone presencial
│   │   ├── video.svg             # Ícone online
│   │   ├── ticket.svg            # Ícone do botão
│   │   ├── upload.svg            # Ícone de upload
│   │   ├── Festivite.svg         # Logo Festivite
│   │   ├── ColorSelection-1.svg a 11.svg  # Swatches de cores
│   │   └── Aniversario.svg, Casamento.svg, etc.  # Ícones de temas
│   └── img/                      # Pasta para imagens adicionais
└── styles/
    ├── global.css                # Variáveis CSS e estilos globais
    └── index.css                 # Estilos do formulário (665 linhas)
```

## 🎨 Como Usar o Formulário

### 1. Sobre o Evento

- **Título**: Nome do evento
- **Início**: Data e hora de início
- **Fim**: Data e hora de término
- **Tipo**: Presencial ou Online
- **Local**: Endereço ou link do evento
- **Descrição**: Detalhes adicionais

### 2. Personalização

- **Cor Principal**: 11 cores disponíveis (rosa, roxo, azul, verde, amarelo, laranja, vermelho, ciano, lima, índigo, âmbar)
- **Tema do Evento**: Aniversário, Casamento, Natal, Páscoa, Halloween, São João, Formatura, Carnaval, Chá de Bebê, Chá de Panela, Infantil, Outro
- **Estilo**: Claro ou Escuro para o convite
- **Foto da Capa**: Upload de imagem (PNG, JPG, GIF até 5MB)

### 3. Dados para Contato

- **Nome**: Nome do organizador
- **E-mail**: E-mail válido
- **Telefone**: Número de contato
- **Termos**: Três checkboxes obrigatórios

### 4. Enviar

- Clique em "Gerar Convite" (177px × 48px, semibold 16px)

## 🛠️ Tecnologias e Técnicas

### HTML5

- Estrutura semântica com tags apropriadas
- Validação nativa de formulários (`required`, `type="email"`, etc.)
- Inputs customizados (radio, checkbox, file, datetime-local)

### CSS3 Avançado

- **Variáveis CSS**: Sistema de cores com `--color-brand-light`, `--color-text-primary`, etc.
- **Seletor `:has()`**: Gerenciamento de estado sem JavaScript
  - Validação: `.input-group:has(input:invalid:not(:placeholder-shown))`
  - Tema toggle: `.theme-toggle-checkbox:checked~body`
- **Pseudo-classes**: `:valid`, `:invalid`, `:checked`, `:placeholder-shown`, `:focus`
- **CSS Grid**: Layouts multi-coluna (2 colunas, 11 colunas para cores)
- **Flexbox**: Alinhamento e distribuição de componentes
- **Custom Properties**: Troca dinâmica de temas
- **Transitions e Animations**: Efeitos suaves em hover e estados

### Validação CSS-Only

```css
/* Exemplo de validação sem JavaScript */
.input-group:has(input:invalid:not(:placeholder-shown)) .error-wrapper {
  display: flex;
}

.input-group input:invalid:not(:placeholder-shown) {
  border-color: var(--color-feedback-success); /* #FF5959 */
  background-color: rgba(255, 89, 89, 0.05);
}
```

### Checkboxes Customizados

```css
/* Checkbox com check SVG inline */
.frame-wrapper input[type="checkbox"]:checked {
  border-color: var(--color-brand-medium);
  background-size: 16px; /* Mostra o check */
}
```

## 🎓 Conceitos Demonstrados

### 1. CSS-Only State Management

- Uso do seletor `:has()` para controlar estados visuais baseados em inputs
- Sem necessidade de JavaScript para validação ou alternância de tema

### 2. Sistema de Temas com CSS Variables

```css
/* Tema escuro (padrão) */
:root {
  --color-text-primary: #c8cdd0;
  --color-shape-primary: #131516;
}

/* Tema claro (quando toggle ativado) */
.layout-wrapper:has(#estilo-claro:checked) {
  --color-brand-light: #59b2ff;
}
```

### 3. Validação em Tempo Real

- Erros aparecem apenas quando o campo é tocado (`:not(:placeholder-shown)`)
- Border vermelha e fundo suave em campos inválidos
- Ícone de erro aparece dinamicamente

### 4. Design Responsivo

- Flexbox e Grid para layouts adaptáveis
- `align-items: flex-start` para alinhar logo e formulário no topo
- Padding ajustado para alinhamento visual perfeito

## 📋 Especificações de Design

### Tipografia

- **Títulos principais** (Sobre o evento, Personalização, Dados para contato): `18px`, `bold 700`, `--color-text-secondary`
- **Labels de campos**: `14px`, `regular 400`, `--color-text-primary (#C8CDD0)`
- **Subtítulos** (Tipo, Tema, Estilo): `0.95rem`, `normal`, `--color-text-secondary`
- **Botão**: `16px`, `semibold 600`, `--color-text-secondary`

### Cores (Brand)

- `--color-brand-light: #59B2FF` (azul claro - check dos checkboxes)
- `--color-brand-medium: #3487CF` (azul médio - hover do botão)
- `--color-brand-dark: #1D6FB6` (azul escuro - botão)

### Componentes

- **Botão Gerar Convite**: 177px × 48px
- **Checkbox**: 20px × 20px com border-radius 4px
- **Logo e Formulário**: Alinhados no topo sem padding-top no aside

## 📝 Validação Implementada

### Campos Validados

✅ **E-mail**: Formato válido (pattern HTML5)  
✅ **Telefone**: Preenchimento obrigatório  
✅ **Nome**: Campo obrigatório  
✅ **Título**: Campo obrigatório  
✅ **Datas**: Início e fim obrigatórios  
✅ **Tipo**: Presencial ou Online (radio obrigatório)  
✅ **Cor**: Seleção obrigatória  
✅ **Tema**: Seleção obrigatória  
✅ **Termos**: Todos os 3 checkboxes obrigatórios

### Feedback Visual

- ❌ **Border vermelha** em campos inválidos
- ❌ **Fundo vermelho suave** (rgba(255, 89, 89, 0.05))
- ❌ **Mensagem de erro** em vermelho (#FF5959)
- ❌ **Ícone de alerta** ao lado da mensagem

## 🌓 Sistema de Temas

### Tema Escuro (Padrão)

- Fundo: `#131516`, `#212427`
- Texto: `#C8CDD0`, `#F9F9F9`
- Input: `#1C1F21`

### Tema Claro

- Ativa quando `#estilo-claro` está checked
- Define apenas `--color-brand-light: #59B2FF`

### Toggle de Tema

- Checkbox oculto controla o tema via CSS `:checked~` combinator
- Transição suave de 0.3s

## 🔧 Customização

### Adicionar Nova Cor

1. Crie `ColorSelection-12.svg` em `assets/icons/`
2. Adicione no HTML:
   ```html
   <label class="color-option color-12">
     <input type="radio" name="cor" value="cor-12" />
     <img src="assets/icons/ColorSelection-12.svg" alt="Cor 12" />
   </label>
   ```
3. Não precisa CSS adicional (já está estilizado)

### Mudar Cores do Tema

Edite `styles/global.css`:

```css
:root {
  --color-brand-light: #SUA_COR;
  --color-brand-medium: #SUA_COR;
  --color-brand-dark: #SUA_COR;
}
```

### Adicionar Novo Tema de Evento

1. Crie o SVG em `assets/icons/SeuTema.svg`
2. Adicione no HTML na seção `.tema-options`

## ❓ Troubleshooting

**Validação não funciona:**

- Verifique se o navegador suporta `:has()` (Chrome 105+, Firefox 121+)
- Limpe o cache (Ctrl+F5 ou Cmd+Shift+R)

**Checkboxes sem estilo:**

- Verifique se o SVG do check está sendo carregado
- Confirme que `appearance: none` está aplicado

**Tema não alterna:**

- Verifique se o input `#estilo-claro` existe no HTML
- Confirme que o CSS usa o seletor correto

**Logo e formulário desalinhados:**

- Confirme que `.aside-container` tem `padding: 0 35px 35px`
- Verifique `align-items: flex-start` no `.layout-wrapper`

## 🚀 Performance

- **CSS otimizado**: 665 linhas bem estruturadas
- **Sem JavaScript**: Validação e temas puramente CSS
- **SVG inline**: Check dos checkboxes (evita request adicional)
- **Carregamento rápido**: Apenas HTML, CSS e SVGs

## 📄 Licença

Este projeto foi desenvolvido pelo Leandro e é fornecido como material educacional e de portfólio.

---

**Desenvolvido com ❤️ - Demonstração de CSS Avançado e Técnicas Modernas**
