# Google-Chrome-Erros
##Error Google Chrome (https)

>Isso é um bug do Chrome atual.

Na libertação Chrome 44 (versão 44.0.2403.89), parece 
que o navegador recebeu um pequeno bug significativo.
É o envio do HTTPS: 1 em cada solicitação do header padrão.
Isso provavelmente foi concebido como uma melhoria da segurança,
para sugerir HTTPS para o servidor sempre que possível, mas isso está
travando o WordPress e outras instalações de servidor web em todo o lugar.


Eu comentei o código no arquivo woocommerce.php

#####wp-content\plugins\woocommerce\woocommerce.php

```
/*if ( ! isset( $_SERVER['HTTPS'] ) ) {
    if ( ! empty( $_SERVER['HTTP_HTTPS'] ) ) {
      $_SERVER['HTTPS'] = $_SERVER['HTTP_HTTPS'];
        } elseif ( ! empty( $_SERVER['HTTP_X_FORWARDED_PROTO'] ) && $_SERVER['HTTP_X_FORWARDED_PROTO'] == 'https' ) {
          $_SERVER['HTTPS'] = '1';
        }
    }*/
```

A maioria dos problemas são por conta do plugin Woocommerce, porém, você pode verificar se o erro ocorre com algum outro plugin.
O Google está planejando um patch de emergência para a próxima atualização. Assim que sair, você pode voltar com o plugin para seu estado normal.

Refência:
>https://ma.ttias.be/chrome-44-sending-https-header-by-mistake-breaking-web-applications-everywhere/




