# Aula 02 - Primeiros Passos no ComfyUI: Interface, Nós e Primeiro Workflow SDXL

Nesta aula partimos de uma tela em branco e construímos, passo a passo, o primeiro workflow completo de geração de imagens com SDXL. Você vai entender o que são nós, como eles se conectam, o que cada parte do modelo faz (UNET, CLIP e VAE) e como configurar os parâmetros do KSampler para obter bons resultados. Ao final, você vai gerar sua primeira imagem dentro do ComfyUI.

## 🛠️ Requisitos e Instalação

### Requisitos

- ComfyUI instalado e funcionando (ver Aula 01).
- Modelo **JuggernautXL** (ou outro checkpoint SDXL) disponível em [Civitai](https://civitai.com) — buscar pelo autor Render Fusion.
- GPU NVIDIA com pelo menos 6 GB de VRAM recomendado para SDXL em 1024x1024.

### Instalação do Modelo

1. Baixe o arquivo `.safetensors` do JuggernautXL no Civitai.
2. Mova o arquivo para a pasta:
   ```
   ComfyUI/models/checkpoints/
   ```
3. Reinicie o ComfyUI ou use o botão **Refresh** para que o modelo apareça no nó Load Checkpoint.

### Carregando o Workflow da Aula

1. Baixe o arquivo `gerando_imagem_aula_02.json` desta pasta.
2. No ComfyUI, acesse **Workflow > Open** e selecione o arquivo baixado.
3. Certifique-se de que o modelo `juggernautXL_ragnarokBy.safetensors` (ou equivalente SDXL) está selecionado no nó **Load Checkpoint**.

## 📂 Arquivos da Aula

| Arquivo | Descrição |
|---|---|
| `gerando_imagem_aula_02.json` | Workflow SDXL text-to-image completo construído durante a aula |

## 🎯 O que aprendemos:

- Como configurar a interface do ComfyUI: limpar o workspace, ativar o ReRoot Beta e escolher o tema.
- A anatomia de um modelo SDXL: **UNET** (cérebro da geração), **CLIP** (encoder de texto com CLIP-L e CLIP-G) e **VAE** (conversor de espaço latente para pixels).
- Como montar um workflow text-to-image do zero com os nós: Load Checkpoint, CLIP Text Encode (positivo e negativo), KSampler, Empty Latent Image, VAE Decode e Save Image.
- O papel de cada conexão entre os nós e por que ela é necessária.
- Parâmetros recomendados para o KSampler com SDXL: Steps 20–30, CFG 4–7, Sampler Euler ou DPM++ 2M, Scheduler Normal ou Beta.
- Como estruturar um prompt: sujeito + ação + ambiente + iluminação + modificadores.
- Como salvar e exportar o workflow para reutilização nas próximas aulas.

## 🚀 Desafio Prático

Monte o workflow SDXL seguindo os passos da aula e gere uma imagem usando a estrutura de prompt: **sujeito + ação + ambiente + iluminação + modificadores**. Experimente ajustar o CFG e o número de steps para ver como os resultados mudam. Compartilhe sua imagem nos comentários do vídeo.

---

_Curso ComfyUI: Renderizando High-End AI Images - Professor Renato Aloi_
