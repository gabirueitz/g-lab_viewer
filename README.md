# G-Lab Studio 3D • Visualizador Técnico de Modelos STL

Aplicação web estática, leve e responsiva projetada para que clientes da **G-Lab Studio 3D** possam inspecionar peças e protótipos 3D diretamente pelo navegador do celular ou computador, sem necessidade de baixar arquivos pesados ou instalar softwares de CAD/fatiamento.

---

## 🚀 Funcionalidades

- **Renderização 3D Direta**: Decodificação e exibição de geometrias STL via **Three.js** com iluminação técnica de estúdio.
- **Integração com Google Drive**: Carregamento automático de peças através do ID ou link público de compartilhamento.
- **Geração de Links Compartilháveis**: Permite enviar ao cliente uma URL direta com a peça já pré-carregada (`?id=ID_DO_ARQUIVO`).
- **Cotas Milimétricas Reais (1:1)**:
  - **X**: Largura (mm)
  - **Y**: Profundidade (mm)
  - **Z**: Altura (mm)
- **Seletor de Cores e Resinas**: 9 opções de acabamentos técnicos (Cinza Mecânico, Chumbo Grafite, Preto Fosco, Branco Técnico, Azul Industrial, Laranja Protótipo, Vermelho Terracota, Verde Militar e Amarelo Ouro).
- **Interface Mobile-Friendly**: Rotação com 1 dedo, zoom por pinça com 2 dedos e deslocamento (pan) com 2 dedos.
- **Ferramentas de Navegação**: Giro automático, recentralização/enquadramento com um toque e grade de solo milimétrica.
- **Sem Servidor de Backend**: Arquivo único `index.html` estático, sem *cold start* (abertura instantânea).

---

## 📁 Estrutura do Projeto

O projeto é intencionalmente mantido em um único arquivo autônomo para facilitar deploys, atualizações e portabilidade:

```text
├── index.html       # Aplicação completa (HTML5 + Tailwind CSS + Three.js)
└── README.md        # Documentação do projeto
```

---

## 🛠️ Como Publicar no GitHub Pages (Passo a Passo)

1. Crie um repositório público no [GitHub](https://github.com) (ex: `glab-viewer`).
2. Faça o upload do arquivo `index.html`.
3. Acesse **Settings** > **Pages** no menu lateral.
4. Na seção **Branch**, selecione `main` (ou `master`) e a pasta `/ (root)`. Clique em **Save**.
5. Aguarde cerca de 1 a 2 minutos. O GitHub gerará sua URL pública:
   ```text
   https://seu-usuario.github.io/glab-viewer/
   ```

---

## 🌐 Como Configurar Subdomínio Próprio (Opcional)

Para utilizar um domínio profissional como `viewer.glabstudio3d.com.br`:

1. No GitHub:
   - Vá em **Settings** > **Pages** > **Custom domain**.
   - Digite `viewer.glabstudio3d.com.br` e clique em **Save**.
2. No seu provedor de domínio (Registro.br, Cloudflare, Hostinger, etc.):
   - Adicione uma entrada DNS do tipo `CNAME`:
     - **Tipo:** `CNAME`
     - **Nome / Host:** `viewer`
     - **Destino:** `seu-usuario.github.io.`
3. Após a propagação do DNS, marque a opção **Enforce HTTPS** na página de configurações do GitHub Pages.

---

## 📦 Como Usar com Arquivos do Google Drive

### 1. Preparar o arquivo no Google Drive
1. Faça upload do arquivo `.stl` no seu Google Drive.
2. Clique com botão direito no arquivo > **Compartilhar** > altere o acesso para **"Qualquer pessoa com o link"** (permissão de **Leitor**).
3. Copie o link gerado, por exemplo:
   ```text
   https://drive.google.com/file/d/1tX8B_yK9ABCdef1234567890/view?usp=sharing
   ```
   *(O trecho `1tX8B_yK9ABCdef1234567890` é o ID do arquivo).*

### 2. Gerar o link para o cliente
Você pode enviar o link já formatado:
```text
https://seu-usuario.github.io/glab-viewer/?id=1tX8B_yK9ABCdef1234567890
```
*Ou abrir o seu visualizador, clicar no botão **Google Drive**, colar o link e usar o botão **Copiar Link p/ Cliente**.*

---

## 📱 Controles de Navegação

| Ação | No Celular | No Computador (Mouse) |
| :--- | :--- | :--- |
| **Rotacionar** | Arrastar com 1 dedo | Botão esquerdo + arrastar |
| **Zoom** | Gesto de pinça com 2 dedos | Scroll / roda do mouse |
| **Mover (Pan)** | Arrastar com 2 dedos juntos | Botão direito + arrastar |

---

## ⚙️ Tecnologias Utilizadas

- [Three.js](https://threejs.org/) (r128) - Motor gráfico WebGL
- [STLLoader](https://threejs.org/docs/#examples/en/loaders/STLLoader) - Decodificação de malhas STL binárias e ASCII
- [OrbitControls](https://threejs.org/docs/#examples/en/controls/OrbitControls) - Interações de toque e mouse
- [Tailwind CSS](https://tailwindcss.com/) - Estilização e responsividade via CDN

---

Desenvolvido para **G-Lab Studio 3D** • Visualização Técnica de Modelos