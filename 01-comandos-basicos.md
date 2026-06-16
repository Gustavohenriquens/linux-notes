# Comandos Básicos
   
  ### Teclado
  - Listar teclados : localectl list-keymaps 
  - Trocar para teclado Brasileiro : loadkeys br-abnt2

  ### Fontes
  - Listar fontes : ls /usr/share/kbd/consolefonts
  - Trocar fontes : setfont "nome da fonte" ex : setfont ter-c20n.psf.gz

  ### Internet
  - Conectar a Internet sem fio : iwctl
      Resultado :
      - [iwd] # 
       - Sair do iwd : exit
  - Verificar internets : device list
  - Confirmar internet pegando : ping "url de site" ex : archlinux.org

  ### Horário
  - Horário e o sistema sicronizado : timedatectl

  ### Disco - Repatição
  - lista todos os discos e suas partições no sistema : fdisk -l
  - Entrar no dico : fdisk /dev/sda
    - Criar tabela : o
    - Cria a partição do sistema : n
      - p (Cria ate 4 partições) - E (Cria mais de 4 partições)
      - t : (É comando que muda o tipo/etiqueta de uma partição já existente)
      - 8E : É o código hexadecimal que identifica o tipo de partição como "Linux LVM" na tabela MBR. É só uma "etiqueta"/metadado dizendo: "essa partição vai ser usada com LVM".

    - Transforma a partição /dev/sda2 em um Physical Volume (PV)  : pvcreate /dev/sda2
    - Criar um VG chamado vg_arch : vgcreate vg_arch /dev/sda2

    - lvcreate -L 2G -n lv_swap vg_arch 
      - lvcreate : Cria um Logical Volume(as cadas dentro do terreno)
      - -L 2G : Define o tamanho 2 Gigabytes
      - -n lv_swap : Define o nome do volume
      -  vg_arch : Diz de onde tirar esse espaço : Do volume Group que criamos antes.

    - lvcreate -l 100%FREE -n lv_home vg_arch
      - -l 100%FREE : Usa todo o espaço que sobrou no Volume Group, inves de definir uma quantidade.
      
    - lvs : Verifica todos os volumes





# Conceitos

   ### Partição
   - Vamos pensar em um HD/SSD, basicamente é dividir isso em varias partes.
     Ex : 200GB para o sistema Linux
          500GB para arquivos
          300GB para backup

   ### MBR
    - Ele define onde cada partição vai ser locado dentro do disco. Onde começa e termina no disco.Basicamente é so um índice/mapa.

   ### LVM
    - É uma camada extra entre as partições físicas do disco e o sistema de arquivos.
    
   ### PV 
    - É o volume físico que o LVM vai utulizar;
    - É a porta de entrada para o LVM.

   ### VG
    - É o grupo de volumes;
    - Ele junta um ou mais PVs e cria um pool único de armazamento.

   ### LV 
    - Volume lógico criado dentro do VG.







# Navegação no Sistema
    - Partition number : Número de identificação da partição (1, 2, 3...). Aqui você pode apenas apertar Enter.
    - First sector (setor inicial) : Onde a partição vai começar. Aqui você pode apenas apertar Enter.
    - Last sector (setor final) : Onde a partição termina. É aqui que você define o tamanho. ex : +512M
      





# Manipulação de Arquivos e Diretórios

# Visualização de Conteúdo

# Busca e Filtragem

# Processos

# Informações do Sistema

# Redirecionamento e Pipes

# Exemplos

# Observações

# Links úteis
