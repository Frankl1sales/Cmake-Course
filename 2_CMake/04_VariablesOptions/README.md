
# **CMake Project: Variables and Options**

Este README descreve o uso dos comandos e etapas para configurar, gerar e compilar um projeto C++ usando o CMake.

---

## **1. Estrutura do Projeto**

O projeto contém dois diretórios principais: 

- **`src/`**: Contém o código da biblioteca (`Library`).
- **`app/`**: Contém o código para criar o executável (`Executable`).

---

## **2. Comandos Utilizados**

### **2.1. Configuração Inicial**
Navegue até o diretório `build` para organizar os arquivos gerados pelo CMake:

```bash
cd build
```

### **2.2. Geração dos Arquivos de Build**
Execute o seguinte comando para configurar o projeto:

```bash
cmake ..
```

Saída esperada:
- Detecta os compiladores C e C++.
- Configura as opções definidas no arquivo `CMakeLists.txt`.
- Cria os arquivos de build no diretório `build`.

---

### **2.3. Compilação**
Para compilar o projeto, use:

```bash
cmake --build .
```

Saída esperada:
- Compila a biblioteca no diretório `src/` como um arquivo estático (`libLibrary.a`).
- Gera o executável no diretório `app/` como `Executable`.

---

### **2.4. Compilação com Opção Personalizada**
Você pode ativar/desativar a compilação do executável usando a variável `COMPILE_EXECUTABLE`. Por exemplo:

```bash
cmake .. -DCOMPILE_EXECUTABLE=ON
```

- **`-DCOMPILE_EXECUTABLE=ON`**: Ativa a compilação do executável.
- **`-DCOMPILE_EXECUTABLE=OFF`**: Apenas compila a biblioteca, sem o executável.

Após configurar, execute novamente:

```bash
cmake --build .
```

---

### **2.5. Limpeza e Recompilação**
Para limpar os arquivos gerados e recompilar, use:

```bash
make
```

Este comando executa as etapas:
1. Remove o diretório `build`.
2. Cria o diretório `build` novamente.
3. Configura os arquivos de build.

Recompile entrando no diretório `build`:

```bash
cd build
cmake ..
cmake --build .
```

---

## **3. Saída Final**

- **Biblioteca**: `build/src/my_lib/libLibrary.a`
- **Executável**: `build/app/Executable`

---

## **4. Dependências**

- **Compilador**: GCC 11.4.0 ou compatível.
- **CMake**: Versão 3.22 ou superior.
