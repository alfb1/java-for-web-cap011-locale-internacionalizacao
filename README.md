# java-for-web-cap011-locale-internacionalizacao

02-07-20 

In�cio

 1.Constru��o da camada de acesso a dados.
 
 2.Tabela cheque
      Create table cheque (
	      cheque int(11) not null,
		  conta  int(11) not null,
		  data_cadastro date not null,
		  situacao char(1) not null,
		  lancamento int(11) default null,
		  
		  primary key( cheque, conta),
		  
		  key 'fk_cheque_lancamento' ('lancamento'),
          key 'fk_cheque_conta' ('conta')		   ,
		  
		  constraint 'fk_cheque_conta' foreign key ('conta')
		    references 'conta_bancaria' ('cod_conta') on delete cascade,
		  constraint 'fk_cheque_lancamento' foreign key ('lancamento')
		    references 'lancamento' ('codigo') on delete cascade
		  );
 Obs.: A tabela acima ser� criada automaticamente pelo Hibernate.
 
 3.Cria��o da classe de chave composta ChequeId.

 4.Cria��o da classe cheque. 
 
 5.Cria��o da interface ChequeDAO.
 
 6.Construcao da camada de visualiza��o
 
 7.Internacionaliza��o