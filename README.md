# Connect Linkar the database

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
    
