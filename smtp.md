#### SMTP

Após o estabelecimento de uma conexão entre emissor (cliente) e receptor (servidor), o exemplo seguinte ilustra uma sessão SMTP. Na conversação seguinte, "C:" designa as mensagens do cliente, e "S:" as mensagens do servidor. Na maioria dos computadores, uma conexão pode ser estabelecida usando o comando telnet no emissor, por exemplo:

```

C: MAIL FROM:<Smith@Alpha.ARPA>

S: 250 OK

C: RCPT TO:<Jones@Beta.ARPA>

S: 250 OK

C: RCPT TO:<Green@Beta.ARPA>

S: 550 No such user here

C: RCPT TO:<Brown@Beta.ARPA>

S: 250 OK

C: DATA

S: 354 Start mail input; end with <CRLF>.<CRLF>

C: Blah blah blah...

C: ...etc. etc. etc.

C: <CRLF>.<CRLF>

S: 250 OK

```
