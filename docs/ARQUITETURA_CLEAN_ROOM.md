# Arquitetura Clean-Room (Anti-DMCA & Zero Assets Protegidos)

## Princípios Obrigatórios
1. **Separação Estrita Código vs. Conteúdo:**
   - **No repositório:** apenas código de runtime recompilado/rewritten, shims de GPU/áudio (WebGPU/WebGL/WebAudio) e documentação técnica.
   - **Fora do repositório:** qualquer textura, áudio, modelo, vídeo, ROM, ISO ou binário proprietário original.
2. **Carregamento Local pelo Usuário (`File System Access API`):**
   - No navegador, o usuário seleciona sua cópia local legítima (`showOpenFilePicker()` / `showDirectoryPicker()`), validada por hash local sem upload para nuvem.
3. **Higiene Antes de Todo Commit Público:**
   - Verificar `.gitignore` contra `*.iso`, `*.bin`, `*.elf`, `SCUS_*`, `.env`, `*.key`.
   - Executar varredura automática garantindo ausência de segredos ou caminhos locais absolutos do sistema (`$HOME`, `%USERPROFILE%`).
