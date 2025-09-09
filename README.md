# **black**_**hole**

Black hole simulation project

Aqui está o código bruto do buraco negro, tudo ficará dentro de src e bin, caso você queira copiar os arquivos.

Estou escrevendo isto enquanto começo o projeto (espero concluí-lo ;D). Eis o que pretendo fazer:

1. Ray tracing: adicionar ray tracing à simulação gravitacional para simular lente gravitacional.

2. Disco de acreção: simular o disco de acreção usando ray tracing + halos.

3. Curvatura do espaço-tempo: demonstrar visualmente o "alçapão no espaço-tempo" que são os buracos negros, usando uma grade (grid) do espaço-tempo.

[opcional] tentar fazer rodar em tempo real ;D

Espero que funcione :/

## **Requisitos para compilação:**

1. Compilador C++ compatível com C++17 ou superior

2. [Cmake](https://cmake.org/)

3. [Vcpkg](https://vcpkg.io/en/)

4. [Git](https://git-scm.com/)

## **Instruções de build**

1. Clone o repositório:
	-  `git clone https://github.com/kavan010/black_hole.git`
2. CD no diretório recém-clonado:
	- `cd ./black_hole` 
3. Instale as dependências com o vcpkg:
	- `vcpkg install`
4. Obtenha o caminho do arquivo de toolchain do vcpkg para CMake:
	- `vcpkg integrate install`
	- Isto exibirá algo como : `CMake projects should use: "-DCMAKE_TOOLCHAIN_FILE=/path/to/vcpkg/scripts/buildsystems/vcpkg.cmake"`
5. Crie um diretório de build:
	- `mkdir build`
6. Configure o projeto com o CMake:
	-  `cmake -B build -S . -DCMAKE_TOOLCHAIN_FILE=/path/to/vcpkg/scripts/buildsystems/vcpkg.cmake`
	-  Use o caminho do toolchain do vcpkg obtido acima
7. Compile o projeto:
	- `cmake --build build`
8. Execute o programa
	- os executáveis estarão na pasta build.

## **Como o código funciona:**

2D: simples — basta executar/compilar 2D_lensing.cpp com as dependências necessárias instaladas.

3D: black_hole.cpp e geodesic.comp trabalham em conjunto para acelerar a simulação usando GPU: essencialmente é enviado um UBO e o geodesic.comp realiza os cálculos pesados com esses dados.

Deve funcionar com as dependências necessárias instaladas, entretanto, eu só testei no Windows com a minha GPU, então não tenho certeza sobre outras plataformas/GPUs.
