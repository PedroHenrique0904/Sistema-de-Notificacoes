# Sistema-de-Notificacoes

interface Notificacao {
    void enviar(String mensagem);
}

class NotificacaoEmail implements Notificacao {

    @Override
    public void enviar(String mensagem) {
        System.out.println("Enviando e-mail: " + mensagem);
    }
}

class NotificacaoSms implements Notificacao {

    @Override
    public void enviar(String mensagem) {
        System.out.println("Enviando SMS: " + mensagem);
    }
}

class NotificacaoWhatsApp implements Notificacao {

    @Override
    public void enviar(String mensagem) {
        System.out.println("Enviando WhatsApp: " + mensagem);
    }
}

class ServicoNotificacao {

    public void notificarCliente(Notificacao notificacao, String mensagem) {
        notificacao.enviar(mensagem);
    }
}

public class Main {

    public static void main(String[] args) {

        ServicoNotificacao servico = new ServicoNotificacao();

        NotificacaoEmail email = new NotificacaoEmail();
        NotificacaoSms sms = new NotificacaoSms();
        NotificacaoWhatsApp whatsapp = new NotificacaoWhatsApp();

        servico.notificarCliente(email, "Sua compra foi aprovada!");
        servico.notificarCliente(sms, "Código de verificação: 1234");
        servico.notificarCliente(whatsapp, "Seu pedido saiu para entrega!");
    }
}
