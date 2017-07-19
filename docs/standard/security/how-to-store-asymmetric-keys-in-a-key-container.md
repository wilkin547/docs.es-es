---
title: "How to: Store Asymmetric Keys in a Key Container | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "cryptography [.NET Framework], asymmetric keys"
  - "storing asymmetric keys"
  - "keys, asymmetric"
  - "encryption keys"
  - "keys, storing in key containers"
  - "asymmetric keys [.NET Framework]"
  - "encryption [.NET Framework], asymmetric keys"
  - "decryption keys"
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# How to: Store Asymmetric Keys in a Key Container
Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local.  Si debe almacenar una clave privada, utilice un contenedor de claves.  Para obtener más información sobre contenedores de claves, consulte esta [Understanding Machine\-Level and User\-Level RSA Key Containers](../Topic/Understanding%20Machine-Level%20and%20User-Level%20RSA%20Key%20Containers.md).  
  
### Para crear una clave asimétrica y guardarla en un contenedor de claves  
  
1.  Cree una instancia nueva de una clase <xref:System.Security.Cryptography.CspParameters> y pase el nombre que quiera darle al contenedor de claves al campo <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=fullName>.  
  
2.  Cree una instancia nueva de una clase que derive de la clase <xref:System.Security.Cryptography.AsymmetricAlgorithm> \(normalmente, **RSACryptoServiceProvider** o **DSACryptoServiceProvider**\) y pase el objeto **CspParameters** creado previamente a su constructor.  
  
### Para eliminar la clave de un contenedor de claves  
  
1.  Cree una instancia nueva de una clase **CspParameters** y pase el nombre que quiera darle al contenedor de claves al campo **CspParameters.KeyContainerName**.  
  
2.  Cree una instancia nueva de una clase que derive de la clase **AsymmetricAlgorithm** \(normalmente, **RSACryptoServiceProvider** o **DSACryptoServiceProvider**\) y pase el objeto **CspParameters** creado previamente a su constructor.  
  
3.  Establezca la propiedad **PersistKeyInCSP** de la clase que deriva de **AsymmetricAlgorithm** en **false** \(**False** en Visual Basic\).  
  
4.  Llame al método **Clear** de la clase que deriva de **AsymmetricAlgorithm**.  Este método libera todos los recursos de la clase y borra el contenedor de claves.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear una clave asimétrica, guardarla en un contenedor de claves, recuperarla posteriormente y eliminarla del contenedor.  
  
 Observe que el código de los métodos `GenKey_SaveInContainer` y `GetKeyFromContainer` es similar.  Si especifica el nombre de un contenedor de claves para un objeto <xref:System.Security.Cryptography.CspParameters> y lo pasa a un objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> con la propiedad <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> o la propiedad <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> establecidas en true, ocurre lo siguiente.  Si no existe un contenedor de claves con el nombre especificado, se crea uno y la clave se conserva.  Si no existe un contenedor de claves con el nombre especificado, la clave del contenedor se carga automáticamente en el objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> actual.  Por lo tanto, el código del método `GenKey_SaveInContainer` conserva la clave porque se ejecuta primero, mientras que el código del método `GetKeyFromContainer` carga la clave porque se ejecuta en segundo lugar.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
 _  
  
Public Class StoreKey  
  
    Public Shared Sub Main()  
        Try  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
        Catch e As CryptographicException  
            Console.WriteLine(e.Message)  
        End Try  
    End Sub  
  
    Public Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        ' name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key added to container:  {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub GetKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Delete the key entry in the container.  
        rsa.PersistKeyInCsp = False  
  
        ' Call Clear to release resources and delete the key from the container.  
        rsa.Clear()  
  
        Console.WriteLine("Key deleted.")  
    End Sub  
End Class  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
  
public class StoreKey  
  
{  
    public static void Main()  
    {  
        try  
        {  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
        }  
        catch(CryptographicException e)  
        {  
            Console.WriteLine(e.Message);  
        }  
  
    }  
  
    public static void GenKey_SaveInContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key added to container: \n  {0}", rsa.ToXmlString(true));  
    }  
  
    public static void GetKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : \n {0}", rsa.ToXmlString(true));  
    }  
  
    public static void DeleteKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Delete the key entry in the container.  
        rsa.PersistKeyInCsp = false;  
  
        // Call Clear to release resources and delete the key from the container.  
        rsa.Clear();  
  
        Console.WriteLine("Key deleted.");  
    }  
}  
```  
  
```Output  
  
            Clave agregada al contenedor:  
<RSAKeyValue> Información de clave A</RSAKeyValue>  
Clave recuperada del contenedor:  
<RSAKeyValue> Información de clave A</RSAKeyValue>  
Clave eliminada.  Clave agregada al contenedor:  
<RSAKeyValue> Información de clave B</RSAKeyValue>  
Clave eliminada.    
```  
  
## Vea también  
 [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)   
 [Encrypting Data](../../../docs/standard/security/encrypting-data.md)   
 [Decrypting Data](../../../docs/standard/security/decrypting-data.md)   
 [Servicios criptográficos](../../../docs/standard/security/cryptographic-services.md)