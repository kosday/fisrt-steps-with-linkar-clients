# Connect Linkar the database and read a record

# C#
		CredentialsOptions credentialOptions = new CredentialsOptions(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test");    
		LinkarClt _LinkarClt = new LinkarClt();    
		string error = _LinkarClt.Login(credentialOptions);    
		...    
		string error = _LinkarClt.Logout();
		
		ReadOptions readOptions = new ReadOptions(false, false, false, false, false);
		LkData _responselkdata = client.Read("LK.CUSTOMERS", "2", "", readOptions, "", 600);
    
# VB
		Dim _credentialOptions As CredentialsOptions
		Dim lkclient As LinkarClt
		Dim ResponseError As String = ""
		_credentialOptions = New CredentialsOptions(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test")
		ResponseError = lkclient.Login(_credentialOptions)
    		...
    		lkclient.Logout()
    
    		Dim responselkdata As LkData
		Dim _readOptions As ReadOptions = New ReadOptions(False, False, False, False, False)
		responselkdata = client.Read("LK.CUSTOMERS", "2", "", _readOptions, "", 600)
    
# Java
		CredentialsOptions credentialsOptions = new CredentialsOptions(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test");
		LinkarClt _LinkarClt = new LinkarClt();
		String error =  _LinkarClt.Login(credentialsOptions);
		...
		String error = _LinkarClt.Logout();
    
		ReadOptions readOptions = new ReadOptions(false, false, false, false, false);
		LkData responselkdata = client.Read("LK.CUSTOMERS", "2", "", readOptions, "", 600);
		
# EXCEL
		Set crd = New CredentialsOptions        
		Call crd.InitializeProperties(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test")
		Set lkClt = New LinkarClt
		err = lkClt.Login(crd, "", 600)
		...
		err = lkClt.Logout()
		
		Dim rop As ReadOptions
		Set rop = New ReadOptions
		Call rop.InitializeProperties(False, False, False, False, False)
		Set responselkdata = client.Read("LK.CUSTOMERS", "2", "", rop)
    
# PHP Windows (LinkarClientCOM Library)
		$crd = new COM("LinkarCommon.CredentialsOptions");
		$crd -> InitializeProperties("127.0.0.1", "E1", 11200, "admin", "admin", "ES", "Test");
		$lkClt = new COM("LinkarClient.LinkarClt");
		$error = $lkClt -> Login($crd);
		...
		$lkClt -> Logout();
		
		$rop = new COM("LinkarCommon.ReadOptions");
		$rop -> InitializeProperties(false, false, false, false, false);			
		$responselkdata = $client -> Read("LK.CUSTOMERS", "2", "", $rop);
    
# PHP Linux extension (LinkarClientC Library)
		$crdOpt = LkCreateCredentialOptions("127.0.0.1", "E1", 11300, "admin", "admin", "ES" , "Test");
		$hasError = "";
		$customVars = "";
		$receiveTimeout = -1;
		$loginResult = LkLogin($crdOpt, $hasError, $customVars, $receiveTimeout);
		if (!$hasError)
		{
			$connectionInfo = $loginResult;
			// ...
			$lkStringLogout = LkLogout($connectionInfo, $hasError, $customVars, $receiveTimeout);
		}
		else
		{
			echo "LOGIN ERROR: {$loginResult}<br />";
		}

		$rop_calculated = 1; // TRUE
		$rop_conversion = 0; // FALSE
		$rop_formatSpec = 0; // FALSE
		$rop_originalRecords = 0; // FALSE
		$rop_dictionaries = 0; // FALSE
		$rop_readOptions = LkCreateReadOptions($rop_calculated, $rop_conversion, $rop_formatSpec, $rop_originalRecords, $rop_dictionaries);

		$hasError = "";
		$responseStringRead = LkRead($connectionInfo, $hasError, "LK.CUSTOMERS", "2", "", $readOptions, $IO_FORMAT_MV, "", -1);
