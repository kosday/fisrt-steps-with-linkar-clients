#Connect Linkar the database

#C#
		CredentialsOptions credentialOptions = new CredentialsOptions(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test");
		LinkarClt _LinkarClt = new LinkarClt();
		string error = _LinkarClt.Login(credentialOptions);
		...
		string error = _LinkarClt.Logout();
#VB
		Dim _credentialOptions As CredentialsOptions
		Dim lkclient As LinkarClt
		Dim ResponseError As String = ""
		_credentialOptions = New CredentialsOptions(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test")
		ResponseError = lkclient.Login(_credentialOptions)
		...
		lkclient.Logout()

#Java
		CredentialsOptions credentialsOptions = new CredentialsOptions(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test");
		LinkarClt _LinkarClt = new LinkarClt();
		String error =  _LinkarClt.Login(credentialsOptions);
		...
		String error = _LinkarClt.Logout();
#EXCEL
		Set crd = New CredentialsOptions        
		Call crd.InitializeProperties(127.0.0.1, "E1", 11200, "admin", "admin", "ES", "Test")
		Set lkClt = New LinkarClt
		err = lkClt.Login(crd, "", 600)
		...
		err = lkClt.Logout()
#PHP Windows (LinkarClientCOM Library)
		$crd = new COM("LinkarCommon.CredentialsOptions");
		$crd -> InitializeProperties("127.0.0.1", "E1", 11200, "admin", "admin", "ES", "Test");
		$lkClt = new COM("LinkarClient.LinkarClt");
		$error = $lkClt -> Login($crd);
		...
		$lkClt -> Logout();
#PHP Linux extension (LinkarClientC Library)
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







