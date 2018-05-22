#### TCP-IP

TCP-IP possui 4 camadas sendo que o início se dá com o programa conversando na camada de aplicação. Nesta camada você vai encontrar protocolos como o SMTP (para e-mail), FTP (para transferência de arquivos) e HTTP (para navegar na internet) e cada tipo de programa fala para um protocolo diferente da camada de Aplicação, dependendo do propósito do programa.

Depois de processar a requisição, o protocolo na camada de Aplicação vai falar com outro protocolo na camada de Transporte, usualmente o TCP. Esta camada é responsável por pegar o dado enviado pela camada de Aplicação, dividindo este dado em pacotes a fim de enviar ele para a camada inferior, a da Internet. Também, durante o recebimento do dados, a camada de Transporte é responsável por colocar os pacotes de dados recebidos da camada de Internet em ordem (os dados podem ser recebidos fora de ordem) e também checar se o conteúdo dos pacotes estão intactos.

Na camada da Internet, nós temos o IP (Internet Protocol), que pega os pacotes recebidos da camada de Transporte e adiciona uma informação de endereço virtual. Exemplo: adiciona o endereço do computador que está enviando dados e o endereço do computador que vai receber estes dados. Estes endereços virtuais são chamados de endereços IP. Então o pacote é enviado para a camada inferior, Interface de Rede e quando dos dados chegam nesta camada, eles são chamados de datagramas.

A Interface de Rede vai pegar os pacotes enviados pela camada de Internet e enviar através da rede (ou receber da rede, se o computador estiver recebendo dados). O que vai ter dentro desta camada vai depender do tipo de rede que o computador estiver inserido. Hoje em dia, o tipo de rede mais utilizado para comunicação entre computadores é a Ethernet (que é avaliada em diferentes faixas de velocidade) e pode ser cabeada (cabo de par trançado CAT5 ou CAT6) ou WI-FI (sem fio). Ainda dentro da camada de Interface de Rede Ethernet, você deve encontrar camadas Ethernet como a LLC (Logic Link Control), MAC (Media Access Control) e a Física que é o meio físico (cabo por exemplo). Os pacotes transmitidos através da rede são chamados de quadros.

| Camada | Exemplo |
| ---- |
| 4 - Aplicação (5ª, 6ª e 7ª camada OSI) |	HTTP, HTTPS, FTP, DNS |
| 3 - Transporte (4ª camada OSI) |	TCP, UDP, SCTP |
| 2 - Internet (3ª camada OSI) |	Para TCP/IP o protocolo é IP, MPLS |
| 1 - Enlace (Interface com Rede) (1ª e 2ª camada OSI) |	Ethernet, Wi-Fi, Modem, etc |

##### Curios

###### Transporte

- O UDP fornece integridade de dados (via um checksum) mas não fornece entrega garantida; já o TCP fornece tanto integridade dos dados quanto garantia de entrega (retransmitindo até que o destinatário receba o pacote).

- O UDP é tipicamente usado por aplicações como as de mídia de streaming (áudio, vídeo etc), onde a chegada na hora é mais importante do que confiabilidade, ou para aplicações de simples requisição/resposta como pesquisas de DNS, onde o overhead de configurar uma conexão confiável é desproporcionalmente largo.

###### Enlace

- A camada de linking pode também ser um VPN (Virtual Private Network, Rede Privada Virtual) ou túnel, onde pacotes da camada de internet, ao invés de serem enviados através de uma interface física, são enviados usando um protocolo de tunneling e outra (ou a mesma) suíte de protocolos. O VPN ou túnel é usualmente estabelecido além do tempo, e tem características especiais que a transmissão direta por interface física não possui (por exemplo, ele pode criptografar os dados que passam através dele). Esse uso recursivo de suíte de protocolos pode ser confuso uma vez que a "camada" de enlace é agora uma rede inteira. Mas é um método elegante para implementar funções frequentemente complexas. Embora seja necessário muito cuidado para prevenir que um pacote já empacotado e enviado através de um túnel seja mais uma vez empacotado e reenviado pelo mesmo.
