# Testes com Python

👋 Olá, Seja Bem-vindo(a) ao 'Testes com Python'.

# Projeto 'Testes com Python' do curso:

## [Testes automatizados: TDD com Python](https://cursos.alura.com.br/course/tdd-com-python)

### Aulas

<details>
    <summary>Por que testar?</summary>
    <ul>
        <li>Preparando o ambiente</li>
        <li>Projeto inicial</li>
        <li>Introdução</li>
        <li>Conhecendo o domínio</li>
        <li>Implementando o avaliador de leilões</li>
        <li>Começando com testes de unidade</li>
        <li>Começando a testar</li>
        <li>Rodando o teste no terminal</li>
        <li>Testes e Produtividade</li>
        <li>Mãos à obra!</li>
        <li>O que aprendemos?</li>
    </ul>
</details>

<details>
    <summary>Boas Práticas e mais alguns testes</summary>
    <ul>
        <li>Criando um novo teste</li>
        <li>Renomeando os testes</li>
        <li>Mais testes e classes de equivalência</li>
        <li>Isolando a criação do cenário</li>
        <li>Projeto atual</li>
        <li>Criando cenários de testes</li>
        <li>Outros métodos da TestCase</li>
        <li>Como nomear um teste?</li>
        <li>Mãos à obra!</li>
        <li>O que aprendemos?</li>
    </ul>
</details>

<details>
    <summary>Remodelando as classes de domínio</summary>
    <ul>
        <li>Um pouco de encapsulamento</li>
        <li>Estado e comportamento</li>
        <li>Projeto atual</li>
        <li>Diga, não pergunte</li>
        <li>Lei de Demeter, ou o Princípio do menor conhecimento</li>
        <li>Para saber mais - Cópia Profunda</li>
        <li>Faça como eu fiz na aula</li>
        <li>O que aprendemos?</li>
    </ul>
</details>

<details>
    <summary>Novas regras de negócio e testando exceções</summary>
    <ul>
        <li>Duas novas regras e novos testes</li>
        <li>Testando exceções e TDD</li>
        <li>Uma conversa sobre passos de bebê</li>
        <li>Projeto atual</li>
        <li>Testando uma exceção</li>
        <li>É preciso fazer baby steps?</li>
        <li>Mãos à obra!</li>
        <li>O que aprendemos?</li>
    </ul>
</details>

<details>
    <summary>Adicionando funcionalidades na classe usuário</summary>
    <ul>
        <li>Conhecendo a Pytest</li>
        <li>Primeiros testes com Pytest</li>
        <li>Um pouco mais de testes</li>
        <li>Testando exceções e fixtures</li>
        <li>Projeto atual</li>
        <li>Conferindo a execução</li>
        <li>Pytest fixtures e classes de testes</li>
        <li>Mãos à obra!</li>
        <li>O que aprendemos?</li>
    </ul>
</details>

<details>
    <summary>Refatorando o projeto</summary>
    <ul>
        <li>Isolando as condições</li>
        <li>Criando uma exceção ao negócio</li>
        <li>Conclusão</li>
        <li>Legibilidade de código</li>
        <li>Refatorando o domínio</li>
        <li>Projeto atual</li>
        <li>O que aprendemos?</li>
    </ul>
</details>


# Notas das aulas:

Para executar um script python, faça conforme o exemplo abaixo:
```sh
docker-compose run --rm app python aulas/01.py
```

## Testes com UnitTest:

Para executar a suite de testes do python, faça conforme o exemplo abaixo:
```sh
docker-compose run --rm app python -m unittest leilao/test_leilao.py
```

Para executar a suite de testes do python via coverage, faça conforme o exemplo abaixo:
```sh
docker-compose run --rm app coverage run -m unittest leilao/test_leilao.py
```

Para gerar o coverage report, faça conforme o exemplo abaixo:
```sh
docker-compose run --rm app coverage html
```

Para abri o coverage report no seu Chrome, faça conforme o exemplo abaixo:
```sh
google-chrome src/htmlcov/index.html
```

## Testes com PyTest:
Dentro do projeto:
```sh
docker-compose run --rm app python -m pytest tests/test_leilao.py
```
Fora do projeto:
```sh
docker-compose run --workdir="/" --rm app python -m pytest tests/test_leilao.py
```

A pasta de testes:
```sh
docker-compose run --workdir="/" --rm app python -m pytest tests/
```

Apenas um teste:
```sh
docker-compose run --workdir="/" --rm app python -m pytest tests/test_usuario.py::nome_do_teste
```

Coverage da pasta testes:
```sh
docker-compose run --workdir="/" --rm app coverage run -m pytest tests/
```

Gerar coverage report da pasta testes:
```sh
docker-compose run --workdir="/tests" --rm app coverage html
```

Abrir coverage report da pasta testes:
```sh
google-chrome tests/htmlcov/index.html
```

## Listar pacotes:
```sh
docker-compose run --rm app pipdeptree
```

## Sobre o projeto:

### Permissões de arquivos:

Ao se criar migrações, adicionar libs ou qualquer outro comando que crie arquivos dentro do contâiner Docker o proprietário para edição se torna o contâiner, sendo assim você precisará rodar o comando abaixo para alterar essas permissões e você poder editar:

```sh
sudo chown -R $USER:$USER .
```

# Exigências

**:warning: Atenção:** É necessário que os desenvolvedores usem o Docker no seu ambiente de desenvolvimento.

- **🛠 Modo Desenvolvimento Docker**
    - :computer: [Linux Ubuntu LTS](https://ubuntu.com/download/desktop)
    - 🐳 [Docker](https://docs.docker.com/engine/installation/) Deve estar instalado.
    - 🐳 [Docker Compose](https://docs.docker.com/compose/) Deve estar instalado.
    - **💡 Dica:** [Documentação do Docker](https://docs.docker.com/)

# Instalando

## 🐳 Modo Desenvolvimento com Docker

Após instalar o docker e docker-compose, estando na pasta raiz do projeto, execute:

```sh
docker-compose up
```

Para se certificar que os seus containers subiram corretamente, todos os containers deve estar com o status `UP`, execute:

```sh
docker-compose ps -a
```

Para acessar o container da aplicação, execute:

```sh
docker-compose run --rm app bash
```

Para derrubar e subir a instância do docker novamente, execute:

```sh
docker-compose down && docker-compose up
```

# Referências utilizadas

[1° Conteinerização de scripts em Python](https://github.com/claudimf/containerized_python)

[2° Base do projeto](https://github.com/alura-cursos/testes-python)

[3° Montando cenários de testes com o Pytest](https://www.alura.com.br/artigos/montando-cenarios-de-testes-com-o-pytest)

[4° Coverage.py](https://coverage.readthedocs.io/en/coverage-5.5/)

[5° An Introduction to Unit Testing in Python](https://www.freecodecamp.org/news/an-introduction-to-testing-in-python/)

[6° How to Create Documentation from Your Python Tests](https://www.freecodecamp.org/news/how-to-create-documentation-from-your-python-tests/)

[7° Outras formas comuns de nomear os testes](https://dzone.com/articles/7-popular-unit-test-naming)

[8° Como fazer uma cópia de uma lista no Python](https://www.alura.com.br/artigos/como-fazer-copia-de-lista-python)

[9° PyTest](https://docs.pytest.org/en/6.2.x/)