# java-for-web-cap011-locale-internacionalizacao

02-07-20 

Início

 1.Construção da camada de acesso a dados.
 
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
 Obs.: A tabela acima será criada automaticamente pelo Hibernate.
 
 3.Criação da classe de chave composta ChequeId.

 4.Criação da classe cheque. 
 
 5.Criação da interface ChequeDAO.
 
 6.Construcao da camada de visualização
 
 7.Internacionalização