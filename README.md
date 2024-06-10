# trilha-java-basico
modelamos um iPhone que desempenha os papéis de Reprodutor Musical, Aparelho Telefônico e Navegador na Internet, usando interfaces para definir os comportamentos esperados. A classe IPhone implementa essas interfaces, fornecendo funcionalidades específicas para cada um desses papéis. Este exemplo demonstra como a orientação a objetos e a reutilização de código podem ser usadas para criar componentes modulares e reutilizáveis em um sistema complexo.

public interface ReprodutorMusical {
    void play();
    void pause();
    void stop();
}
public interface AparelhoTelefonico {
    void ligar(String numero);
    void atender();
    void iniciarCorreioVoz();
}

public interface NavegadorInternet {
    void exibirPagina(String url);
    void adicionarNovaAba(String url);
    void atualizarPagina();
}
public class IPhone implements ReprodutorMusical, AparelhoTelefonico, NavegadorInternet {
    private String marca;
    private String modelo;

    public IPhone(String marca, String modelo) {
        this.marca = marca;
        this.modelo = modelo;
    }

    // Métodos de ReprodutorMusical
    @Override
    public void play() {
        System.out.println("Reproduzindo música...");
    }

    @Override
    public void pause() {
        System.out.println("Música pausada.");
    }

    @Override
    public void stop() {
        System.out.println("Música parada.");
    }

    // Métodos de AparelhoTelefonico
    @Override
    public void ligar(String numero) {
        System.out.println("Ligando para " + numero + "...");
    }

    @Override
    public void atender() {
        System.out.println("Atendendo chamada...");
    }

    @Override
    public void iniciarCorreioVoz() {
        System.out.println("Iniciando correio de voz...");
    }

    // Métodos de NavegadorInternet
    @Override
    public void exibirPagina(String url) {
        System.out.println("Exibindo página: " + url);
    }

    @Override
    public void adicionarNovaAba(String url) {
        System.out.println("Adicionando nova aba com página: " + url);
    }

    @Override
    public void atualizarPagina() {
        System.out.println("Atualizando página...");
    }

    // Métodos adicionais
    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public static void main(String[] args) {
        IPhone iphone = new IPhone("Apple", "iPhone 13");

        // Usando ReprodutorMusical
        iphone.play();
        iphone.pause();
        iphone.stop();

        // Usando AparelhoTelefonico
        iphone.ligar("123-4567");
        iphone.atender();
        iphone.iniciarCorreioVoz();

        // Usando NavegadorInternet
        iphone.exibirPagina("https://www.apple.com");
        iphone.adicionarNovaAba("https://www.example.com");
        iphone.atualizarPagina();
    }
}


