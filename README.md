
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Consultor de NF-e | Consulta Acadêmica</title>

    <style>
        * {
            box-sizing: border-box;
        }

        html,
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, Helvetica, sans-serif;
            color: #555;
            background:
                radial-gradient(#ddd 0.7px, transparent 0.7px);
            background-size: 5px 5px;
        }

        body {
            min-height: 100vh;
        }

        /* ==============================
           TOPO
        ============================== */

        .topo {
            height: 130px;

            background:
                linear-gradient(
                    90deg,
                    #fff 0%,
                    #fffaf0 35%,
                    #f7e5b9 100%
                );

            border-bottom: 1px solid #d6b16e;

            position: relative;
            overflow: hidden;
        }

        .topo::after {
            content: "";

            position: absolute;

            right: -100px;
            top: -100px;

            width: 650px;
            height: 300px;

            background:
                radial-gradient(
                    circle,
                    rgba(255,255,255,.8) 0 8px,
                    transparent 9px
                );

            opacity: .6;
        }

        .topo-conteudo {
            max-width: 1000px;

            margin: auto;

            height: 100%;

            display: flex;

            align-items: center;

            position: relative;

            z-index: 2;
        }

        .logo {
            width: 140px;

            font-size: 58px;

            font-weight: bold;

            font-style: italic;

            color: #e8eeee;

            text-shadow:
                2px 2px 2px #555,
                -1px -1px 0 #fff;

            letter-spacing: -7px;
        }

        .logo span {
            color: #8ab02c;
        }

        .titulo-topo {
            margin-left: 20px;

            color: #d17b20;

            font-size: 19px;

            letter-spacing: 2px;
        }

        .titulo-topo small {
            display: block;

            color: #aaa;

            font-size: 11px;

            letter-spacing: 0;

            margin-top: 6px;
        }

        /* ==============================
           MENU
        ============================== */

        .menu {
            height: 28px;

            background: #f7f7f7;

            border-bottom: 1px solid #d59d58;
        }

        .menu-conteudo {
            max-width: 1000px;

            margin: auto;

            display: flex;

            height: 100%;
        }

        .menu a {
            padding: 6px 30px;

            border-right: 1px solid #e1ad67;

            color: #555;

            font-size: 12px;

            text-decoration: none;
        }

        .menu a:hover {
            background: #fff1db;
        }

        .home {
            width: 38px;

            padding: 5px !important;

            text-align: center;

            background: #edae59;

            color: white !important;

            font-size: 17px !important;
        }

        /* ==============================
           CAMINHO
        ============================== */

        .breadcrumb {
            max-width: 1000px;

            margin: 12px auto;

            font-size: 10px;

            color: #b46d2c;
        }

        .breadcrumb strong {
            background: #bbb;

            color: white;

            padding: 5px 10px;

            margin-right: 10px;
        }

        /* ==============================
           CONTAINER
        ============================== */

        .pagina {
            max-width: 1000px;

            margin: auto;

            padding-bottom: 50px;
        }

        .titulo-consulta {
            display: inline-block;

            margin-top: 30px;
            margin-bottom: 28px;

            padding: 4px 12px;

            background: #e4a454;

            color: white;

            font-weight: bold;

            font-size: 14px;
        }

        /* ==============================
           CAIXA CONSULTA
        ============================== */

        .consulta {
            background: #fffdf9;

            border: 1px solid #ead5b6;

            min-height: 250px;

            padding: 35px 60px;

            box-shadow:
                0 2px 5px rgba(0,0,0,.03);
        }

        .campo-label {
            display: block;

            color: #c87527;

            font-size: 12px;

            margin-bottom: 4px;
        }

        .campo {
            width: 100%;
            max-width: 650px;

            height: 40px;

            border: 2px solid #222;

            border-radius: 4px;

            padding: 4px 10px;

            font-size: 14px;

            outline: none;
        }

        .campo:focus {
            border-color: #e19a47;

            box-shadow:
                0 0 4px rgba(225,154,71,.4);
        }

        /* ==============================
           AVISO AUTENTICO
        ============================== */

        .aviso-AUTENTICO {
            margin-top: 12px;

            max-width: 650px;

            padding: 10px 12px;

            background: #fff5d9;

            border: 1px solid #e8ce8e;

            color: #795b20;

            font-size: 11px;

            line-height: 1.5;
        }

        /* ==============================
           BOTÕES
        ============================== */

        .botoes {
            margin-top: 12px;

            display: flex;

            gap: 5px;
        }

        .btn {
            border: 0;

            padding: 7px 18px;

            font-size: 12px;

            color: #555;

            background:
                linear-gradient(
                    #fff,
                    #e8c18d
                );

            border: 1px solid #e4c08d;

            box-shadow:
                0 1px 2px rgba(0,0,0,.2);

            cursor: pointer;
        }

        .btn:hover {
            background:
                linear-gradient(
                    #fff,
                    #dca963
                );
        }

        /* ==============================
           RESULTADO
        ============================== */

        #resultado {
            display: none;

            margin-top: 25px;
        }

        .resultado-box {
            border: 1px solid #d6c39f;

            background: white;

            box-shadow:
                0 2px 8px rgba(0,0,0,.08);

            animation: aparecer .4s ease;
        }

        @keyframes aparecer {
            from {
                opacity: 0;
                transform: translateY(10px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .resultado-topo {
            background: #f1dfbe;

            border-bottom: 1px solid #d5b986;

            padding: 12px 18px;

            color: #8a571f;

            font-weight: bold;

            font-size: 14px;
        }

        .aviso {
            margin: 15px;

            padding: 12px;

            background: #fff5d9;

            border: 1px solid #e8ce8e;

            color: #795b20;

            font-size: 12px;

            line-height: 1.5;
        }

        /* ==============================
           STATUS
        ============================== */

        .status-area {
            margin: 15px;
        }

        .status {
            display: inline-flex;

            align-items: center;

            gap: 7px;

            padding: 7px 11px;

            background: #e9f7ed;

            border: 1px solid #9dccaa;

            color: #287d40;

            font-size: 11px;

            font-weight: bold;
        }

        .status-dot {
            width: 8px;

            height: 8px;

            background: #32a852;

            border-radius: 50%;
        }

        /* ==============================
           DADOS
        ============================== */

        .dados {
            display: grid;

            grid-template-columns:
                repeat(2, 1fr);

            gap: 1px;

            margin: 15px;

            background: #ddd;

            border: 1px solid #ddd;
        }

        .dado {
            background: #fff;

            padding: 14px;
        }

        .dado small {
            display: block;

            color: #a56b31;

            font-size: 10px;

            margin-bottom: 5px;

            text-transform: uppercase;
        }

        .dado strong {
            color: #333;

            font-size: 14px;
        }

        /* ==============================
           PRODUTO
        ============================== */

        .produto {
            margin: 15px;

            border: 1px solid #ddd;
        }

        .produto-titulo {
            background: #f5f0e7;

            padding: 10px;

            color: #805725;

            font-weight: bold;

            font-size: 12px;
        }

        .produto-info {
            padding: 20px;

            display: flex;

            justify-content: space-between;

            align-items: center;

            gap: 20px;
        }

        .produto-nome {
            font-size: 21px;

            font-weight: bold;

            color: #333;
        }

        .produto-descricao {
            margin-top: 7px;

            font-size: 11px;

            color: #888;
        }

        .valor {
            color: #287d40;

            font-size: 25px;

            font-weight: bold;

            white-space: nowrap;
        }

        /* ==============================
           CÓDIGO DA CONSULTA
        ============================== */

        .chave-exibida {
            margin: 15px;

            padding: 12px;

            background: #f8f8f8;

            border: 1px solid #ddd;

            font-family: monospace;

            font-size: 13px;

            color: #444;

            word-break: break-all;
        }

        /* ==============================
           ERRO
        ============================== */

        .erro {
            display: none;

            margin-top: 15px;

            padding: 12px;

            background: #fff0ef;

            border: 1px solid #e2aaa5;

            color: #a33b32;

            font-size: 12px;
        }

        /* ==============================
           OBSERVAÇÕES
        ============================== */

        .observacoes {
            margin-top: 25px;

            color: #b76627;

            font-size: 12px;

            line-height: 1.5;
        }

        .observacoes h3 {
            font-size: 13px;

            margin-bottom: 8px;
        }

        .observacoes ol {
            margin-top: 5px;

            padding-left: 20px;
        }

        /* ==============================
           RODAPÉ
        ============================== */

        footer {
            border-top: 1px solid #d9bd92;

            background: #f7f3eb;

            padding: 15px;

            text-align: center;

            color: #888;

            font-size: 10px;
        }

        /* ==============================
           RESPONSIVO
        ============================== */

        @media(max-width:700px) {

            .topo {
                height: 105px;
            }

            .topo-conteudo {
                padding: 0 15px;
            }

            .logo {
                font-size: 42px;

                width: 100px;
            }

            .titulo-topo {
                font-size: 13px;
            }

            .menu a {
                padding: 7px 10px;

                font-size: 10px;
            }

            .menu a:nth-child(n+4) {
                display: none;
            }

            .pagina {
                width: 94%;
            }

            .consulta {
                padding: 25px 20px;
            }

            .dados {
                grid-template-columns: 1fr;
            }

            .produto-info {
                flex-direction: column;

                align-items: flex-start;
            }

            .valor {
                font-size: 21px;
            }
        }
    </style>
</head>

<body>

    <!-- ==============================
         CABEÇALHO
    ============================== -->

    <header class="topo">

        <div class="topo-conteudo">

            <div class="logo">
                NF<span>e</span>
            </div>

            <div class="titulo-topo">

                NOTA FISCAL ELETRÔNICA

                <small>
                    CONSULTA ACADÊMICA DE DOCUMENTOS
                </small>

            </div>

        </div>

    </header>


    <!-- ==============================
         MENU
    ============================== -->

    <nav class="menu">

        <div class="menu-conteudo">

            <a class="home" href="#">
                ⌂
            </a>

            <a href="#">
                Serviços
            </a>

            <a href="#">
                Legislação
            </a>

            <a href="#">
                Documentos
            </a>

            <a href="#">
                Downloads
            </a>

            <a href="#">
                Outros DF-e
            </a>

        </div>

    </nav>


    <!-- ==============================
         BREADCRUMB
    ============================== -->

    <div class="breadcrumb">

        <strong>
            Você está aqui
        </strong>

        Página Principal &gt;
        Serviços &gt;
        Consultar NF-e

    </div>


    <!-- ==============================
         PÁGINA
    ============================== -->

    <main class="pagina">

        <div class="titulo-consulta">
            Consultar NF-e
        </div>


        <!-- ==============================
             CONSULTA
        ============================== -->

        <section class="consulta">

            <label
                class="campo-label"
                for="chave">

                Chave de Consulta

            </label>


            <input
                id="chave"
                class="campo"
                type="text"
                maxlength="60"
                placeholder="Digite a chave de acesso">


            <div class="aviso-AUTENTICO">

                <strong>ATENÇÃO:</strong>

                A consulta
                utiliza dados cadastrados localmente
                para fins de apresentação do projeto.

            </div>


            <!-- BOTÕES -->

            <div class="botoes">

                <button
                    class="btn"
                    onclick="consultar()">

                    Continuar

                </button>

                <button
                    class="btn"
                    onclick="limpar()">

                    Limpar

                </button>

            </div>


            <!-- ERRO -->

            <div
                class="erro"
                id="erro">

                Nenhum registro encontrado
                para a chave informada.

            </div>


            <!-- RESULTADO -->

            <div id="resultado">

                <div class="resultado-box">

                    <div class="resultado-topo">

                        Resultado da consulta acadêmica

                    </div>


                    <div class="aviso">

                        <strong>SIMULAÇÃO ACADÊMICA:</strong>

                        O resultado abaixo representa um
                        cadastro demonstrativo criado para
                        este projeto. Ele não constitui
                        validação oficial de autenticidade
                        fiscal.

                    </div>


                    <!-- STATUS -->

                    <div class="status-area">

                        <div class="status">

                            <span class="status-dot"></span>

                            REGISTRO ENCONTRADO NO CADASTRO

                        </div>

                    </div>


                    <!-- CHAVE -->

                    <div class="chave-exibida">

                        <strong>
                            Chave consultada:
                        </strong>

                        <br><br>

                        <span id="chaveResultado">
                            -
                        </span>

                    </div>


                    <!-- DADOS -->

                    <div class="dados">

                        <div class="dado">

                            <small>
                                Situação
                            </small>

                            <strong>
                                Registro encontrado
                            </strong>

                        </div>


                        <div class="dado">

                            <small>
                                Tipo de documento
                            </small>

                            <strong>
                                NF-e
                            </strong>

                        </div>


                        <div class="dado">

                            <small>
                                Consulta
                            </small>

                            <strong>
                                Sistema VALIDADO
                            </strong>

                        </div>


                        <div class="dado">

                            <small>
                                Cadastro
                            </small>

                            <strong>
                                Local
                            </strong>

                        </div>

                    </div>


                    <!-- PRODUTO -->

                    <div class="produto">

                        <div class="produto-titulo">

                            PRODUTO CADASTRADO

                        </div>


                        <div class="produto-info">

                            <div>

                                <div class="produto-nome">

                                    Titan 160 2027

                                </div>

                                <div class="produto-descricao">

                                    Produto cadastrado
                                    para demonstração
                                    acadêmica.

                                </div>

                            </div>


                            <div class="valor">

                                R$ 21.041,87

                            </div>

                        </div>

                    </div>

                </div>

            </div>

        </section>


        <!-- ==============================
             OBSERVAÇÕES
        ============================== -->

        <section class="observacoes">

            <h3>
                Observações
            </h3>

            <ol>

                <li>
                    Informe a chave para consultar
                    o cadastro demonstrativo.
                </li>

                <li>
                    A página foi desenvolvida
                    exclusivamente para fins DE EMPRESAS DE MOTOS.
                </li>

                <li>
                    Os dados exibidos  substituem
                    uma consulta oficial junto aos
                    órgãos fiscais competentes.
                </li>

            </ol>

        </section>

    </main>


    <!-- ==============================
         RODAPÉ
    ============================== -->

    <footer>

        Sistema AUTENTICO de demonstração
        de consulta de documentos fiscais.

        <br><br>

        —  representa
        um portal oficial da SEFAZ.

    </footer>


    <script>

        /*
        ============================================
        CHAVE CADASTRADA PARA A DEMONSTRAÇÃO
        ============================================
        */

        const chaveCadastrada =
            "522504206436080009216546654654166547565165123";


        /*
        ============================================
        NORMALIZAR CHAVE
        ============================================
        */

        function normalizarChave(valor) {

            return valor
                .replace(/\D/g, "")
                .trim();

        }


        /*
        ============================================
        CONSULTAR
        ============================================
        */

        function consultar() {

            const campo =
                document.getElementById("chave");

            const resultado =
                document.getElementById("resultado");

            const erro =
                document.getElementById("erro");

            const chaveResultado =
                document.getElementById("chaveResultado");


            const chave =
                normalizarChave(campo.value);


            resultado.style.display = "none";

            erro.style.display = "none";


            /*
            Se não digitou nada
            */

            if (!chave) {

                erro.textContent =
                    "Digite uma chave para realizar a consulta.";

                erro.style.display = "block";

                return;

            }


            /*
            COMPARAÇÃO
            */

            if (chave === chaveCadastrada) {

                chaveResultado.textContent =
                    formatarChave(chave);


                resultado.style.display =
                    "block";


                /*
                Rola automaticamente até o resultado
                */

                setTimeout(function() {

                    resultado.scrollIntoView({
                        behavior: "smooth",
                        block: "start"
                    });

                }, 150);


            } else {

                erro.textContent =
                    "Nenhum registro encontrado para a chave informada.";

                erro.style.display =
                    "block";

            }

        }


        /*
        ============================================
        FORMATAR CHAVE
        ============================================
        */

        function formatarChave(chave) {

            /*
            Mantém a visualização em grupos
            */

            return chave.match(/.{1,4}/g).join(" ");

        }


        /*
        ============================================
        LIMPAR
        ============================================
        */

        function limpar() {

            document.getElementById("chave").value = "";

            document.getElementById("resultado").style.display =
                "none";

            document.getElementById("erro").style.display =
                "none";

            document.getElementById("chave").focus();

        }


        /*
        ============================================
        ENTER PARA CONSULTAR
        ============================================
        */

        document
            .getElementById("chave")
            .addEventListener(
                "keydown",
                function(event) {

                    if (event.key === "Enter") {

                        consultar();

                    }

                }
            );

    </script>

</body>

</html>
