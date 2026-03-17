# Spinning Cube (ASCII em C)

## Descrição
Projeto experimental em C para renderizar um cubo rotacionando em ASCII no terminal, usando projeção 3D simples, buffer de profundidade (`z-buffer`) e atualização contínua de frame.

## Objetivo
Estudo de fundamentos gráficos/matemáticos de renderização 3D em modo texto:
- rotação em 3 eixos;
- projeção 3D -> 2D;
- visibilidade com `z-buffer`;
- loop de renderização em terminal.

## Tecnologias
- C
- Biblioteca padrão C (`stdio.h`, `math.h`, `string.h`)
- GCC (ou compilador C compatível)

## Como rodar
> **Estado atual:** o código compila e executa como protótipo de terminal.

Tentativa de build:

```bash
gcc cube.c -lm -o cube
```

Execução:

```bash
./cube
```

## Estrutura
- `cube.c`: implementação única com lógica de rotação, projeção, z-buffer e renderização ASCII.

## Mecânicas implementadas no código
- variáveis globais para ângulos de rotação (`A`, `B`, `C`);
- funções de transformação para coordenadas `X/Y/Z`;
- cálculo por superfície para desenhar faces com caracteres diferentes;
- buffer de profundidade para manter o pixel mais próximo;
- loop infinito de animação com atualização incremental de ângulos.

## Estado atual
- Protótipo funcional em arquivo único.
- Sem sistema de build, testes automatizados ou CI.
- Código ainda focado em estudo (não produção).

## Limitações
- Sem modularização (arquivo único e forte acoplamento global).
- Sem documentação de decisões matemáticas no código.
- Sem controle de FPS/tempo de frame.
- Sem tratamento de portabilidade de terminal.

## Melhorias futuras (pequenas e realistas)
1. Adicionar `Makefile` simples com alvo `run`.
2. Extrair constantes e reduzir estado global.
3. Modularizar em múltiplos arquivos (`math`, `render`, `main`).
4. Adicionar comentários breves sobre as fórmulas de rotação/projeção.
5. Incluir opção de configurar largura/altura via argumentos.

## Aprendizados
Mesmo incompleto, o projeto é útil para estudar:
- fundamentos de pipeline gráfico simplificado;
- impacto de qualidade de código em C (tipagem, nomes e consistência);
- debugging de erros de compilação em projetos legados/protótipos.
