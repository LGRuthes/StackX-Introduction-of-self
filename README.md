Eu desenvolvi este projeto utilizando botões junto com a função "onclick" no qual quando o usuário clica no botão, algum código ira rodar como especificado. 

Ignorando o documento de CSS que seria simplesmente para enfeitar a página, começo adicionando um logo na forma de uma imagem dentro de uma div.
        <div class="Logo">
            <img src="images/StackXLogo.jpg" alt="Logo" width="200px" height="50px"/>
        </div>
        
Após isso, começo a utilizar a main, criando uma div que contêm oque servira como o texto base que será mudado ao clicar no botão. Decidi utilizar H2 para dar uma enfasê no texto. Dei ambos class para poder enfeitar com css, e também ID para que pudesse acessar no código que virá depois.

        <div>
            <h2 class = "msg1" id = "msg1"> Olá, meu nome é Lucas Gabriel e eu sou Desenvolvedor Front-End,</h2>
            <h2 class = "msg2" id = "msg2">Tecnologias que tenho experiência:</h2>
        </div>
        
A seguir, foi adicionado uma div no qual seria a caixa que contem as tecnologias no qual tenho experiência com, usando li para listar cada componente.

       <div class="Caixa">
            <li>
                HTML 
            </li>
            <li>
                CSS
            </li>
            <li>
                JavaScript
            </li>
            <li>
                C#
            </li>
        </div>
        
Crio então os botões, dando eles um ID junto com a syntax onclick para que possa acessa-los depois. Também adiciono imagens/icones junto com o texto para mostrar qual linguagem que o usuário estara clicando em.

       <div class="Buttons">
            
            <button id="PT" onclick="newLanguage('pt')">
                <img src="images/IconBR.jpg" alt="ButtonBR"width="10px" height="10px"/>
                Português</button>
            <button id="EN" onclick="newLanguage('en')">
                <img src="images/IconEN.jpg" alt="ButtonEN"width="10px" height="10px"/>
                English</button>
            <button id="ES" onclick="newLanguage('es')">
                <img src="images/IconSP.jpg" alt="ButtonSP"width="10px" height="10px"/>
                Español</button>


        </div>

Já agora começa o script, no qual crio uma função chamado newLanguage que aceita um string e o utiliza em hash que serve como um fragmento da URL. Então, crio algo que dara reload na página. 

                    <script>

                    function newLanguage(language)
                    {
                        location.hash = language;
                        location.reload();
                    }

Depois crio algo utilizando getElementbyID para que possa acessar as mensagens que quero mudar depois.

                    let msg1 = document.getElementById("msg1")
                    let msg2 = document.getElementById("msg2")

Na próxima sessão, crio o que será o local no qual o código irá acessar o código a ser mudado, especificando o texto de todas as 3 linguagens.

                   let language = 
                    {
                        en:
                        {
                            msg1: "Hello, my name is Lucas Gabriel and I am a Front-End developer,",
                            msg2: "These are the technologies I have experience with:"
                        },
                        pt:
                        {
                            msg1: "Olá, meu nome é Lucas Gabriel e eu sou Desenvolvedor Front-End,",
                            msg2: "Tecnologias que tenho experiência:"
                        },
                        es:
                        {
                            msg1: "Hola, mi nombre es Lucas Gabriel y soy Desarrollador Front-End,",
                            msg2: "Tecnologías en las que tengo experiencia:"
                        },
                    }

Por fim, crio um if statement que primeiramente checa se location.hash é existente, e então, caso o hash seja de uma certa forma, ele mudará os dois textos para a lingua escolhida.

if (window.location.hash)
                {

                    if (window.location.hash == "#en")
                    {
                        msg1.textContent = language.en.msg1;
                        msg2.textContent = language.en.msg2;
                    }
                    else if (window.location.hash == "#es")
                    {
                        msg1.textContent = language.es.msg1;
                        msg2.textContent = language.es.msg2;
                    }

                }
                
                </script>
         

        

    </main>

</body>


</html>


E o resultado final é uma página bem decorada, utlizando CSS, HTML e JavaScript no qual tem uma introdução pessoal breve dizendo quais tecnologias tenho experiência com, e que pode ser vista em 3 linguas diferentes atráves de 3 botões com funções onclick vinculadas a eles.
