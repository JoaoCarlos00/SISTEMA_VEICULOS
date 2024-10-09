# SISTEMA DE VEÍCULOS

Terceiro exercício de sobre Herança

## 🚀 Começando

Um sistema processa dados de veículos de vários tipos. Nesse sistema, todos os automotores possuem modelo, ano de fabricação, montadora, cor, e kilometragem (odômetro). Um automóvel doméstico possui também quantidade máxima de passageiros, tipo de freio e airbag. As motocicletas possuem cilindradas e torque. Os caminhões possuem quantidade de eixos e peso bruto. As bicicletas possuem, modelo, marca, cor, material, quantidade de marchas e amortecedor. Os skates possuem modelo, marca, cor e tipo das rodas. O modelo e ano de fabricação são obrigatórios para todos os veículos.

Todos os atributos devem ser encapsulados e validados quando necessário.

Todas as classes devem ter seus construtores e um método que gera o comando insert desses dados. Para isso, considere o nome classe como o nome da tabela e cada atributo da classe como um campo desta tabela. Pesquisar sobre override pode ser útil.

Crie vários objetos para testar as classes e seus métodos.

### 📋 Códigos

class Veiculo {  // Começo criando uma classe com o modelo que os outros objetos irão seguir como exemplo
    String modelo;
    int anoFabricacao;
    String montadora;
    String cor;
    double kilometragem;

    public Veiculo(String modelo, int anoFabricacao, String montadora, String cor, double kilometragem) {
        this.modelo = modelo;
        this.anoFabricacao = anoFabricacao;
        this.montadora = montadora;
        this.cor = cor;
        this.kilometragem = kilometragem;
    }

    public String gerarInsert() {  // Criei o retorno com as informações pedidas e que serão necessárias
        return "INSERT INTO veiculos (modelo, ano_fabricacao, montadora, cor, kilometragem) VALUES ('" 
                + modelo + "', " + anoFabricacao + ", '" + montadora + "', '" + cor + "', " + kilometragem + ");";
    }
}

class Automovel extends Veiculo {  // Criação da classe Automovel herdando o modelo criado na classe Veiculo, adicionando a quantidade máxima de passageiros, tipo de freio e airbag
    int maxPassageiros;
    String tipoFreio;
    boolean airbag;

    public Automovel(String modelo, int anoFabricacao, String montadora, String cor, double kilometragem,  
                     int maxPassageiros, String tipoFreio, boolean airbag) {
        super(modelo, anoFabricacao, montadora, cor, kilometragem);
        this.maxPassageiros = maxPassageiros;
        this.tipoFreio = tipoFreio;
        this.airbag = airbag;
    }

    @Override  // O conceito que permite que uma subclasse forneça uma implementação específica para um método que já foi definido na superclasse
    public String gerarInsert() {  // Criei o retorno com as informações pedidas e que serão necessárias
        return "INSERT INTO automoveis (modelo, ano_fabricacao, montadora, cor, kilometragem, max_passageiros, tipo_freio, airbag) VALUES ('" 
               + modelo + "', " + anoFabricacao + ", '" + montadora + "', '" + cor + "', " + kilometragem + ", " 
               + maxPassageiros + ", '" + tipoFreio + "', " + airbag + ");";
    }
}

class Motocicleta extends Veiculo {  // Criação da classe Motocicleta que herda da classe Veiculo
    int cilindrada;
    int torque;

    public Motocicleta(String modelo, int anoFabricacao, String montadora, String cor, double kilometragem,
                       int cilindrada, int torque) {
        super(modelo, anoFabricacao, montadora, cor, kilometragem);
        this.cilindrada = cilindrada;
        this.torque = torque;
    }

    @Override  // O conceito que permite que uma subclasse forneça uma implementação específica para um método que já foi definido na superclasse
    public String gerarInsert() {  // Criei o retorno com as informações pedidas e que serão necessárias
        return "INSERT INTO motocicletas (modelo, ano_fabricacao, montadora, cor, kilometragem, cilindrada, torque) VALUES ('" 
               + modelo + "', " + anoFabricacao + ", '" + montadora + "', '" + cor + "', " + kilometragem + ", " 
               + cilindrada + ", " + torque + ");";
    }
}

class Caminhao extends Veiculo {  // Criação da classe Caminhao que herda da classe Veiculo
    int quantidadeEixos;
    double pesoBruto;

    public Caminhao(String modelo, int anoFabricacao, String montadora, String cor, double kilometragem,
                    int quantidadeEixos, double pesoBruto) {
        super(modelo, anoFabricacao, montadora, cor, kilometragem);
        this.quantidadeEixos = quantidadeEixos;
        this.pesoBruto = pesoBruto;
    }

    @Override  // O conceito que permite que uma subclasse forneça uma implementação específica para um método que já foi definido na superclasse
    public String gerarInsert() {  // Criei o retorno com as informações pedidas e que serão necessárias
        return "INSERT INTO caminhões (modelo, ano_fabricacao, montadora, cor, kilometragem, quantidade_eixos, peso_bruto) VALUES ('" 
               + modelo + "', " + anoFabricacao + ", '" + montadora + "', '" + cor + "', " + kilometragem + ", " 
               + quantidadeEixos + ", " + pesoBruto + ");";
    }
}

public class Main {  // Criação da classe que irá fazer os testes
    public static void main(String[] args) {
        Automovel carro = new Automovel("Fusca", 1985, "Volkswagen", "azul", 50000, 4, "hidráulico", true);
        Motocicleta moto = new Motocicleta("CB500", 2020, "Honda", "vermelha", 12000, 500, 45);
        Caminhao caminhao = new Caminhao("Scania", 2015, "Scania", "preto", 250000, 3, 12000);

        System.out.println(carro.gerarInsert());  // Exibe o comando INSERT do automóvel
        System.out.println(moto.gerarInsert());    // Exibe o comando INSERT da motocicleta
        System.out.println(caminhao.gerarInsert()); // Exibe o comando INSERT do caminhão
    }
}



### 🔧 Instalação

* Explicação de como deve ser utilizado o projeto

## 🛠️ Construído com

Ferramentas utilizadas e bibliotecas

* IDE Eclipse

## 📌 Versão

* **Versão 1.0** caso seja atualizado manter a descrição inicial e inserir uma nova linha com descrição da atualização.
* **Versão 1.1** - *Refatoração* *data 09/09/24*

## ✒️ Autores

* João Carlos Ferreira de Araujo RA 248152 -- AC2 Programação Orientada à Objetos

