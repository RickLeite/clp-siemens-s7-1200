# CLP SIEMENS SIMATIC S7-1200 | TIA Portal V15.1

Código de exemplo do programa escrito em LAD demostrado nos 3 vídeos bônus sobre **"Aprenda a Programar CLP do ZERO"** do autor *André Terra* disponível no site [CLP Fácil](https://clpfacil.com.br/).

![](Automation/Aprenda%20a%20Programar%20CLP%20do%20ZERO%20-%20André%20Terra%20-%20CLP%20Fácil/UserFiles/workview.png)

André Terra é um programador 'STEP 7' certificado pela SIEMENS, que disponibiliza vídeos de cursos básicos de forma gratuita e cursos avançados completos de programação em CLP (Controlador Lógico Programável) em seu site, acesse e se inscreva para receber o link dos vídeos bônus!

Esse repositório é uma contribuição pessoal com o objetivo de compartilhar o código-fonte do programa demostrado nos vídeos ao demais estudantes e entusiastas da área, geralmente profissionais desta área não estão habituados com as formas/meios de disponibilizar o código-fonte em repositórios públicos como o GitHub.

## REQUISITOS

O programa foi escrito em [linguagem ladder](https://pt.wikipedia.org/wiki/Linguagem_ladder) através do software [TIA Portal da SIEMENS](https://w3.siemens.com/mcms/automation-software/en/tia-portal-software/step7-tia-portal/step7-basic/Pages/Default.aspx) na versão 15.1.

> Nos vídeos é utilizada a versão 13, não posso garantir se o código escrito na versão 15.1 é suportada pela versão 13!

Para testar o programa em um simulador virtual é utilizado o [S7-PLCSIM V15.1](https://w3.siemens.com/mcms/simatic-controller-software/en/step7/simatic-s7-plcsim/Pages/Default.aspx), que cria e configura CLPs SIEMENS virtuais para teste de programa.

> O PLCSIM é parte integrada da instalação do TIA a parti da versão 14, o TIA Portal V15.1 instala automaticamente o S7-PLCSIM V15.1.
>
> Nos vídeos é emulada no PLCSIM uma **CPU 1214C DC/DC/DC** - Código 6ES7 214-1AG40-0XB0 - Firmware V4.1, como eu tenho disponível para trabalho uma unidade física da **CPU 1215C DC/DC/DC** - Código 6ES7 215-1AG40-0XB0 - Firware V4.2, eu utilizei essa para testes tanto simulado no PLCSIM (virtual) quanto no equipamento real (físico), utilizando a funcionalidade de *SIM tables* no PLCSIM (igual é demostrada nos vídeos) e a *Watch and force tables* do TIA para conseguir simular estados de portas também no equipamento físico. **Por esse motivo esse projeto utiliza a CPU 1215C ao invés da 1214C mostrada nos vídeos!!!**

## COMO UTILIZAR

Para utilizar esse exemplo no seu TIA Portal, basta baixar o projeto é copiar os diretórios **'Aprenda a Programar CLP do ZERO - André Terra - CLP Fácil'** e **'Aprenda a Programar CLP do ZERO - André Terra - CLP Fácil'** dos respectivos diretórios **'Automation'** e **'Simulation'** para os diretórios 'Automation' e 'Simulation' respectivamente no diretório 'Meus Documentos'. Isso vai fazer com que o TIA Portal reconheça e liste automaticamente os projetos.

Caso não deseje copiar as pastas para os diretórios de projetos padrão do TIA, é possível abrir o projeto através dos arquivos `Aprenda a Programar CLP do ZERO - André Terra - CLP Fácil.ap15_1` (Programação) e `Aprenda a Programar CLP do ZERO - André Terra - CLP Fácil.sim15_1` (Simulação).

## SOLUÇÕES DE PROBLEMAS

* **Error "Online connection failed... Module 'CPUcommon' has an incompatible firmware version"**

  **Solução**: Criar uma **Subnet** (PN/IE_1) logo após definir o endereço de IP no projeto, a **Subnet** pode ser criada no bloco acima do bloco que define o IP. Lembre-se de abrir o projeto de simulação no PLCSIM ou criar um novo projeto!!!

## SUGESTÃO DE MELHORIAS (REFATORAÇÃO)

Perceba que na lógica atual o Motor 1 (M1) continua em funcionamento mesmo após a caixa passar pela porta, o ideal é que o Motor M1 deixe de operar quando não houver mais caixa sobre sua plataforma, teoricamente após a liberação do Sensor 2 (S2) que é responsável por verificar se a porta está totalmente aberta juntamente com o Sensor 3 (S3) que identifica quando a caixa já percorreu boa parte da plataforma do Motor 2 (M2). Em engenharia de software chamamos isso de refatoração de código, já em automação industrial gosto de chamar de otimização energética, já que a plataforma do Motor 1 continua a funcionar mesmo sem nenhum objeto sobre ela, gerando gasto de energia elétrica desnecessária para o objetivo fim da automação.

## DÚVIDAS

Por gentileza procurem o *André Terra* que é autor deste projeto através do site [CLP Fácil](https://clpfacil.com.br/), eu só sou mais um entusiasta que assistiu os vídeos, gostou e agora está divulgado como forma de contribuir com essa iniciativa do *André* de compartilhar conhecimento sobre automação industrial.
