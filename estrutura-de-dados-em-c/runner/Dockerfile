# Use a imagem oficial do GCC como base
FROM gcc:latest

# Copie os arquivos do diretório local para o container
COPY . /usr/src/study_c

# Defina o diretório de trabalho
WORKDIR /usr/src/study_c

# Compile o arquivo C (substitua "seu_arquivo.c" pelo nome do seu arquivo)
RUN gcc main.c -o main

# Execute o programa compilado (substitua "seu_programa" pelo nome do seu executável)
CMD ["./main"]
