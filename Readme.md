<p align="center">
    <img src="./src/images/ufc-logo.png" alt="Brasão da Universidade Federal do Ceará." width="250px">
</p>

---

## Sumário
- [O que é backdoor?](#O-que-é-backdoor?)
- [Ferramentas](#ferramentas)
- [Configuração de ambiente](#configuração-de-ambiente)
- [Prática](#prática)

---

## O que é backdoor?

Backdoor é um recurso oculto em um software que concede um certo nível de acesso ao software para quem estiver ciente desse recurso e geralmente não é de conhecimento do propietário do sistema.

Isso permite que um usuário externo possa acessá-lo para realizar algum tipo de modificação no sistema em sí ou em um software específico.

Um backdoor pode ser criado por um desenvolvedor, afim de   realizar manutenções em softwares, porém, é um meio bastante utilizado por usuários mal intencionados para obter acesso ilícito para a realização de algum tipo de ataque, isso permite que eles entrem e saiam da maneira que quiserem, dando-lhes acesso remoto ao sistema.

O funcionamento de um backdoor, estar associado a dois conceitos importantes, são eles:

**_Daemons_**:

Um *daemon* é basicamente um processo de longa duração executado em segundo plano, portanto, é um processo que é executado sem qualquer interação do usuário. Para um usuário comum é completamente invisível e pode até não suspeitar de sua existência.
    
**_Reverse Shell_**:

Ao atacar, os hackers geralmente necessitam obter acesso remoto no sistema alvo.

Uma técnica comum que eles usam para ganhar controle é a vinculação de shell: primeiro o atacante compreende seu sistema, explorando um serviço vulnerável e enviando um *payload*. Este *payload* é na verdade, um shell remoto que abre uma porta no sistema da vítima, que fica a espera do invasor se conectar e executar os comandos.

No entanto, o que acontece se a vítima estiver protegida por um firewall que descarta qualquer requisição de conexão de entrada remota?

<p align="center">
    <img src="./src/images/shell_reverse.jpg" alt="" width="600px">
</p>

O firewall irá bloquear as conexões de entrada, mas não as de saída, porque você sabe... as pessoas precisam acessar a Internet.

Então, em vez de tentar se conectar ao shell que ele colocou na vítima, o invasor apenas construirá seu shell para que ele inicialize a conexão. Tudo o que ele tem que fazer é esperar pacientemente a vítima para se conectar a ele.

<p align="center">
    <img src="./src/images/shell_connected.jpg" alt="" width="600px">
</p>

Desta forma, é possível obter um backdoor invisível que será ignorado pela maioria dos firewalls.

## Ferramentas
Existem diversas ferramentas específicas para criação de backdoors, abaixo, estao descritas algumas dessas dessas ferramentas: 
- [Cryptcat](https://tools.kali.org/maintaining-access/cryptcat)
- [MsfPayload](https://www.offensive-security.com/metasploit-unleashed/msfpayload/)
- [The Fat Rat](https://github.com/Screetsec/TheFatRat)
- [Armitage](https://www.offensive-security.com/metasploit-unleashed/armitage/)
- [Netcat](https://nmap.org/ncat/)

## Configuração do ambiente

Para começar a criar seu primeiro backdoor, será necessário que você possua um sistema para realiza o ataque e o sistema para atacar.

É recomendado a utilização de sistemas linux para a realização do ataque, devido a quantidade gigantesca de ferramentas para a plataforma, você pode usar qualquer sistema linux, porém, recomendamos  a utilização de sistemas criados especialmente para este tipo de atividade, como: [Kali Linux](https://www.kali.org/), [Backbox](https://backbox.org/), [Deft](http://www.deftlinux.net/), entre outros.

Para usar como sistema alvo, você poderá escolher qualquer sistema que seja de seu interesse realizar o ataque, porém, para realizar a prática, disponibilizaremos uma imagem do sistema operacional Windows 7 para que você rode em uma máquina virtual (Recomendamos a utilização do [Virtual Box](https://www.virtualbox.org/)), o sistema está configurado com alguns antivírus para que .

[Clique aqui para obter a imagem do windows 7]()

## Prática

Para a realização desta prática, iremos utilizar a ferramenta The Fat Rat, para realizar o download basta clonar o seu repositório:

1. ```git clone https://github.com/Screetsec/TheFatRat.git```
2. ```cd TheFatRat```
3. ```chmod +x setup.sh```
4. ```sudo ./setup.sh```