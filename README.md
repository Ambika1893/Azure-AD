# Azure-AD
https://learn.microsoft.com/en-us/users/ambikaeswaran-0819/   - Use this for new 


https://learn.microsoft.com/en-us/entra/identity/   - Azure AD study


# Create & Manage Users Via Comd
For Bulk User creations
Option Power Shell type 
  New - mguser

  Create a Password profile value

  
   $Passwordprofile =@{Password = <"passwords>"}

   
  Create New User 

  
    New-mguser Displayname "harditya Siva" -Passwordprofile

    
    $Passwordprofile -MailNickname "HardityaS" -userprincipalname "Hardityas@tcs.com" - Account Enabled

#Bulk User creation for Csv




    $users = Import-Csv -Path "C:\path\to\your\Users.csv"

foreach 


($user in $users) {

    New-MgUser -UserPrincipalName $user.UserName `
    
               -GivenName $user.FirstName `
               -Surname $user.LastName `
               -DisplayName $user.DisplayName `
               -JobTitle $user.JobTitle `
               -Department $user.Department `
               -AccountEnabled $true `
               -MailNickname $user.FirstName `
               -UsageLocation "US" `
               -PasswordProfile @{ForceChangePasswordNextSignIn = $true; Password = "Password"}
}


## Azure Containers

While virtual machines are an excellent way to reduce costs versus the investments that are necessary for physical hardware, they're still limited to a single operating system per virtual machine. If you want to run multiple instances of an application on a single host machine, containers are an excellent choice
