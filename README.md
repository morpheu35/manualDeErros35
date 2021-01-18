# manualDeErros35

Retorno de erros para os seguintes campos:

1- numeroBeneficio: 

	NB: Requisição sem número do benefício (O número do benefício deve ser 		informado)

	HM: Mutuário não identificado (O DV do número do benefício deve ser correto 		e o benefício deve estar presente na base de empréstimo consignado)

	HQ: Benefício é do tipo PA (Na inclusão/averbação, na exclusão por 		portabilidade, na averbação por portabilidade, no refinanciamento e na 		alteração de empréstimo, o benefício informado é de uma espécie (pensão 		alimentícia) que não permite a consignação de empréstimo bancário)
	
	IB: Benefício suspenso/cessado pela APS ou pelo Sisob (A averbação de 		empréstimo, averbação de RMC, inclusão de desconto de cartão, exclusão por 		portabilidade, averbação por portabilidade, refinanciamento, alteração de 		empréstimo e reativação não podem ser realizadas em um benefício que está 		suspenso/cessado pelo INSS ou Sisobi)
	
	IE: Benefício bloqueadopara empréstimo pelo beneficiário (Na averbação de 		empréstimo, averbaçãode RMC, exclusão por portabilidade, refinanciamento e 		alteração de empréstimo, o benefício não pode ter sido bloqueado pelo 		beneficiário)
	
	HR: Quantidade decontratos permitida excedida (A quantidade de contratos 		depende da consignação e do tipo de movimento. Para empréstimo consignado, 		viaja mais e retenção, é permitido a inclusão de até 9 contratos para o 		mesmo benefício, independente da Instituição Financeira, desde que haja 		margem disponível. Para a RMC, o limite é de um único contrato)
	
	H3: É possível que tenha ocorrido uma mudança emergencial de sistema, por
	motivo legal ou outro, ou mesma alguma falha de sistema. Entrar em contato 		com a DATAPREV.
	
	AP: Competência de início de desconto ou data de início ou fim de contrato 		inválida (Ver item 3.8 do manual 09)
	
2- codigoSolicitante:
	
	BC: Requisição sem CBC (O CBC da solicitação (codigoSolicitante)
	do serviço deve ser informado.)
	
	ON: Operação não permitida (O status da associação IF/Operação é diferente 		de Ativa e Suspensa ou não está associada. Verificar com o INSS para efetuar 	a associação)
	
	FH: Operação fora do horário permitido (Cada operação tem seu horário de
	funcionamento, sendo este o mesmo para todas IF´s. IF deverá verificar na 		documentação do sistema o horário da operação)
	
	AB: Tipo de Operação Inválido ( As modalidades possíveis para cada operação 		estão descritas no domínio M e O código solicitante deve ser uma instituição 	conveniada que possui permissão para realizar a operação)
	
	CA: Código do banco inválido (O codigoSolicitante da requisição deve: 
		-Ser igual ao CBC da instituição financeira que foi 				autenticada através do usuário pessoa física;
		-Possuir um convênio ativo para operar consignações)
	
	HS: Benefício não pertence ao banco (O banco está tentando averbar uma
	retenção em benefício para o qual não é o banco pagador) 

3- numeroContrato:
	
	NC: A requisição está sem número de contrato (A requisição está sem número 	de contrato.)

	
	HZ: Não é possível fazer a operação com o empréstimo nesta situação  
		(-Só é possível reativar um contrato que esteja suspenso pelo 				banco.
 		-Só é possível suspender um contrato que esteja ativo ou
		suspenso pela APS.
 		-Só é possível excluir um contrato que não esteja excluído.
		-Só é possível excluir por portabilidade ou refinanciar um contrato 		que esteja ativo)

	HY: Empréstimo inexistente (Só é possível suspender, reativar, excluir, 		excluir por portabilidade, refinanciar e alterar um contrato que tenha sido 		previamente averbado)
	
4- motivoExclusao
	
	ME: o motivo de exclusão do empréstimo é inválido (Os motivos de exclusão de 	empréstimo estão definidos no domínio I)

Além dos erros citados acima, existem os erros/retornos:

	AV: Não é possível realizar a operação até que seja concluído o 	processamento da folha de pagamento do INSS (Na data de hoje está ocorrendo 	o processamento da folha de pagamento do INSS, tendo iniciado na data 		imediatamente seguinte à data limite das operações. Durante este período: 		São represados os processamento dos arquivos CNAB enviados Não são aceitos 		operações on-line (API ou portal de operações) que façam manutenção nos 		empréstimos consignados)
	
	
	OT: O tamanho do(s) campo(s) está incorreto: <campo 1>, <campo 2> (Um ou 		mais campos da solicitação teve o tamanho máximo excedido, ou o tamanho 	mínimo não foi atendido. Consulte o respectivo manual, para obter as 	informações sobre o tamanho do mesmo.)

	OZ: O serviço está suspenso. Motivo: <Motivo> 
