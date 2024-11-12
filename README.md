**Renderizador de Objetos 3D**
Este projeto utiliza o Blender e Python para renderizar modelos 3D a partir de arquivos .glb, gerando imagens em 5 ângulos diferentes com fundo transparente. As imagens geradas podem ser usadas em diversas aplicações, como catálogos de produtos 3D, visualizações interativas ou animações.

**Funcionalidade**
Renderiza modelos 3D em 5 ângulos diferentes (com intervalos de 72 graus) a partir de arquivos .glb.
Salva as imagens renderizadas com fundo transparente (formato PNG).
Criação de backups: Para cada modelo, um arquivo .blend é salvo, contendo a cena do modelo renderizado.
Centralização dos objetos: O código calcula o centro da cena e move todos os objetos para esse centro, garantindo uma visualização equilibrada.
Configuração de luz e câmera: Luz solar é adicionada à cena, e a câmera é posicionada para capturar os ângulos definidos.

**Funcionalidades principais**
Entrada de Modelos:
Importa modelos 3D no formato .glb de um diretório especificado.

**Renderização:**
Gera imagens dos modelos em 5 ângulos diferentes.

**Saída:**
Salva as imagens geradas em um diretório de saída, além de salvar o arquivo .blend para backup.

**Pré-requisitos:**
Blender 3.x: O código foi desenvolvido para rodar no Blender com suporte ao scripting Python.
Python ==3.11.*: Requer a instalação do Python para rodar o script.

**Instalação e Configuração:**
Instalar o Blender:
Baixe e instale a versão mais recente do Blender.
Instalar dependências do Python:

O Blender já vem com o Python embutido, mas é necessário garantir que o bpy e outras dependências estejam corretamente configurados. Se necessário, instale os pacotes extras para integração com o Python do Blender.

**bash
  pip install bpy mathutils
  Preparar os diretórios:**

Defina o diretório de entrada onde os arquivos .glb estão localizados.
Defina o diretório de saída onde as imagens renderizadas serão salvas.
Rodar o Script:

Abra o IDE e carregue o script Python fornecido.
No script, altere os caminhos das variáveis input_dir e output_dir para os diretórios corretos.

**render_3d_objects(
    input_dir="CAMINHO/DO/DIRETÓRIO/DE/ENTRADA",
    output_dir="CAMINHO/DO/DIRETÓRIO/DE/SAÍDA"
)**

**Executar o script:**

Execute o script no compilador. O script irá processar todos os arquivos .glb no diretório de entrada e salvar as imagens renderizadas no diretório de saída.

**Como o Script Funciona**
Leitura e Importação dos Modelos:
O script procura por arquivos .glb no diretório de entrada.

Centralização da Cena:
O código calcula o centro geométrico de todos os objetos na cena e os move para esse ponto central.

Configuração de Luz e Câmera:
Uma luz do tipo 'sun' é adicionada à cena, e a câmera é configurada para capturar os modelos de diferentes ângulos.

Renderização:
O script renderiza a cena de 5 ângulos diferentes e salva as imagens geradas no diretório de saída.

Limpeza:
Após a renderização, o arquivo .blend de backup é removido.
Estrutura do Diretório
A estrutura do diretório de entrada deve ser a seguinte:

input_dir/
    model1.glb
    model2.glb
    model3.glb
    ...
A estrutura do diretório de saída será:

markdown
Copiar código
output_dir/
    model1/
        render_0.png
        render_72.png
        render_144.png
        render_216.png
        render_288.png
        model1.blend
    model2/
        render_0.png
        render_72.png
        render_144.png
        render_216.png
        render_288.png
        model2.blend
    ...
  
  
Personalização
Ângulos de Câmera:
No código, você pode alterar a lista angles para modificar os ângulos de visualização (em graus).

Resolução:
Altere a variável render_resolution para ajustar a resolução das imagens renderizadas (ex: 1920 para 1920x1920).

Posição da Câmera e Luz:
As variáveis camera_location e light_object.location controlam a posição da câmera e da luz na cena, respectivamente.

Contribuindo
Contribuições são bem-vindas! Se você tiver sugestões, correções ou melhorias, sinta-se à vontade para abrir uma issue ou enviar um pull request.

Licença
Este projeto é de código aberto e distribuído sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.

**Exemplo de Uso:
render_3d_objects(
    input_dir="C:/Users/usuario/Projetos/models/",
    output_dir="C:/Users/usuario/Projetos/renders/"
)**
