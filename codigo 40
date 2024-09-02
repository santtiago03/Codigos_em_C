#include <stdio.h>

// Declaração das funções
void inicializarTabuleiro(char tabuleiro[3][3]);
void mostrarTabuleiro(char tabuleiro[3][3]);
int verificarVencedor(char tabuleiro[3][3]);
void jogada(char tabuleiro[3][3], char jogador);

// Função principal
int main() {
    char tabuleiro[3][3];
    int resultado = 0;
    char jogadorAtual = 'X';

    inicializarTabuleiro(tabuleiro);

    // Loop do jogo
    while (resultado == 0) {
        mostrarTabuleiro(tabuleiro);
        jogada(tabuleiro, jogadorAtual);
        
        resultado = verificarVencedor(tabuleiro);

        if (resultado != 0) {
            break;
        }

        // Alterna os jogadores
        jogadorAtual = (jogadorAtual == 'X') ? 'O' : 'X';
    }

    mostrarTabuleiro(tabuleiro);
    
    if (resultado == 1) {
        printf("Jogador %c venceu!\n", jogadorAtual);
    } else {
        printf("O jogo terminou em empate!\n");
    }

    return 0;
}

// Inicializa o tabuleiro com espaços vazios
void inicializarTabuleiro(char tabuleiro[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            tabuleiro[i][j] = ' ';
        }
    }
}

// Mostra o tabuleiro no console
void mostrarTabuleiro(char tabuleiro[3][3]) {
    printf("  0   1   2\n");
    for (int i = 0; i < 3; i++) {
        printf("%d ", i);
        for (int j = 0; j < 3; j++) {
            printf(" %c ", tabuleiro[i][j]);
            if (j < 2) printf("|");
        }
        printf("\n");
        if (i < 2) printf(" ---|---|---\n");
    }
}

// Verifica se há um vencedor ou empate
int verificarVencedor(char tabuleiro[3][3]) {
    // Verificação de linhas
    for (int i = 0; i < 3; i++) {
        if (tabuleiro[i][0] == tabuleiro[i][1] && tabuleiro[i][1] == tabuleiro[i][2] && tabuleiro[i][0] != ' ')
            return 1;
    }

    // Verificação de colunas
    for (int j = 0; j < 3; j++) {
        if (tabuleiro[0][j] == tabuleiro[1][j] && tabuleiro[1][j] == tabuleiro[2][j] && tabuleiro[0][j] != ' ')
            return 1;
    }

    // Verificação de diagonais
    if (tabuleiro[0][0] == tabuleiro[1][1] && tabuleiro[1][1] == tabuleiro[2][2] && tabuleiro[0][0] != ' ')
        return 1;
    if (tabuleiro[0][2] == tabuleiro[1][1] && tabuleiro[1][1] == tabuleiro[2][0] && tabuleiro[0][2] != ' ')
        return 1;

    // Verificação de empate
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (tabuleiro[i][j] == ' ')
                return 0; // Ainda há jogadas possíveis
        }
    }

    return -1; // Empate
}

// Realiza a jogada de um jogador
void jogada(char tabuleiro[3][3], char jogador) {
    int linha, coluna;

    printf("Jogador %c, insira sua jogada (linha e coluna): ", jogador);
    scanf("%d %d", &linha, &coluna);

    while (linha < 0 || linha > 2 || coluna < 0 || coluna > 2 || tabuleiro[linha][coluna] != ' ') {
        printf("Jogada inválida. Tente novamente: ");
        scanf("%d %d", &linha, &coluna);
    }

    tabuleiro[linha][coluna] = jogador;
}
