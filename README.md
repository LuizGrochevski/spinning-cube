# Spinning Cube (ASCII em C)

Renderização de um cubo 3D rotacionando em tempo real no terminal usando caracteres ASCII e projeção em perspectiva.

---

## 🧭 Objetivo

Projeto de estudo focado em fundamentos de computação gráfica de baixo nível:

- rotação 3D nos eixos X/Y/Z  
- projeção 3D → 2D  
- depth buffer (`z-buffer`) simplificado  
- animação contínua em terminal ANSI  

---

## ⚙️ Tecnologias

- C (C99/C11)
- Biblioteca padrão C:
  - `stdio.h`
  - `string.h`
  - `unistd.h`
- `math.h` (link com `-lm`)
- Terminal com suporte a ANSI escape codes

---

## ▶️ Como rodar

### Linux/macOS

```bash
gcc -Wall -Wextra -pedantic cube.c -lm -o cube
./cube
```

### Encerrar

```bash
Ctrl + C
```
## 🧠 Arquitetura (simplificada)

Estrutura atual em arquivo único:
```bash
cube.c
```

### Principais partes:

**Estados globais**
- Ângulos de rotação
- Buffers
- Parâmetros de câmera

**Transformação 3D**
- `calculateX`
- `calculateY`
- `calculateZ`

**Pipeline de renderização**
- `calculateForSurface`
  - projeção
  - cálculo de profundidade
  - escrita no frame buffer

**Loop principal (`main`)**
- limpeza dos buffers
- rasterização das faces
- render no terminal
- atualização dos ângulos

---

## 🎮 Funcionalidades

- Cubo 3D com rotação contínua  
- Projeção em perspectiva  
- Ocultação de superfícies com `z-buffer`  
- Renderização ASCII com diferenciação de faces  
- Animação fluida via reset de cursor (`\x1b[H`)  

---

## 🚧 Estado atual

- Demo funcional em terminal  
- Foco educacional (não produção)  
- Sem interação com usuário  
- Estrutura monolítica  

---

## ⚠️ Limitações

- Parâmetros hardcoded (tamanho, escala, velocidade)  
- Uso intenso de variáveis globais  
- Sem tratamento de resize de terminal  
- Sem controle de FPS / delta time  
- Loop infinito dependente de interrupção manual  

---

## 🔧 Melhorias futuras

- [ ] Parametrização via CLI (tamanho, velocidade, escala)  
- [ ] Encapsular configuração em `struct`  
- [ ] Separar matemática e renderização em módulos  
- [ ] Criar `Makefile`  
- [ ] Melhorar portabilidade (`usleep` → alternativa cross-platform)  

---

## 📚 Aprendizados

Este projeto demonstra, em escala reduzida:

- pipeline gráfico essencial (transformação → projeção → depth test)  
- manipulação manual de coordenadas 3D  
- renderização sem dependência de bibliotecas gráficas  
- trade-offs de design em C (simplicidade vs organização)  

---

## 🧩 Observação

Projeto experimental com foco em aprendizado técnico e exploração de conceitos — não voltado para produção.
