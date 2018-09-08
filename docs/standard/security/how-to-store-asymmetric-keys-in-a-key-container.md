---
title: 'Cómo: Almacenar claves asimétricas en un contenedor de claves'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5cd157f89797406fbe87c3d70c415d7b192d1a9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204843"
---
# <a name="how-to-store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="4fe41-102">Cómo: Almacenar claves asimétricas en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="4fe41-102">How to: Store Asymmetric Keys in a Key Container</span></span>
<span data-ttu-id="4fe41-103">Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="4fe41-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="4fe41-104">Si debe almacenar una clave privada, utilice un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="4fe41-104">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="4fe41-105">Para más información sobre contenedores de claves, consulte [Descripción de los contenedores de claves RSA en el nivel de equipo y de usuario](https://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9).</span><span class="sxs-lookup"><span data-stu-id="4fe41-105">For more information on key containers, see [Understanding Machine-Level and User-Level RSA Key Containers](https://msdn.microsoft.com/library/9a179f38-8fb7-4442-964c-fb7b9f39f5b9).</span></span>  
  
### <a name="to-create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="4fe41-106">Para crear una clave asimétrica y guardarla en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="4fe41-106">To create an asymmetric key and save it in a key container</span></span>  
  
1.  <span data-ttu-id="4fe41-107">Crear una nueva instancia de un <xref:System.Security.Cryptography.CspParameters> clase y pase el nombre que desee darle al contenedor de claves para el <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.</span><span class="sxs-lookup"><span data-stu-id="4fe41-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>  
  
2.  <span data-ttu-id="4fe41-108">Crear una nueva instancia de una clase que deriva el <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase (normalmente **RSACryptoServiceProvider** o **DSACryptoServiceProvider**) y pase creado previamente  **CspParameters** objeto a su constructor.</span><span class="sxs-lookup"><span data-stu-id="4fe41-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
### <a name="to-delete-the-key-from-a-key-container"></a><span data-ttu-id="4fe41-109">Para eliminar la clave de un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="4fe41-109">To delete the key from a key container</span></span>  
  
1.  <span data-ttu-id="4fe41-110">Cree una instancia nueva de una clase **CspParameters** y pase el nombre que quiera darle al contenedor de claves al campo. **CspParameters.KeyContainerName**.</span><span class="sxs-lookup"><span data-stu-id="4fe41-110">Create a new instance of a **CspParameters** class and pass the name that you want to call the key container to the **CspParameters.KeyContainerName** field.</span></span>  
  
2.  <span data-ttu-id="4fe41-111">Cree una instancia nueva de una clase que derive de la clase **AsymmetricAlgorithm** (normalmente, **RSACryptoServiceProvider** o **DSACryptoServiceProvider**) y pase el objeto **CspParameters** creado previamente a su constructor.</span><span class="sxs-lookup"><span data-stu-id="4fe41-111">Create a new instance of a class that derives from the **AsymmetricAlgorithm** class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
3.  <span data-ttu-id="4fe41-112">Establezca la propiedad **PersistKeyInCSP** de la clase que derive de **AsymmetricAlgorithm** en **false** (**False** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4fe41-112">Set the **PersistKeyInCSP** property of the class that derives from **AsymmetricAlgorithm** to **false** (**False** in Visual Basic).</span></span>  
  
4.  <span data-ttu-id="4fe41-113">Llame al método **Clear** de la clase que derive de **AsymmetricAlgorithm**.</span><span class="sxs-lookup"><span data-stu-id="4fe41-113">Call the **Clear** method of the class that derives from **AsymmetricAlgorithm**.</span></span> <span data-ttu-id="4fe41-114">Este método libera todos los recursos de la clase y borra el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="4fe41-114">This method releases all resources of the class and clears the key container.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fe41-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fe41-115">Example</span></span>  
 <span data-ttu-id="4fe41-116">En el ejemplo siguiente se muestra cómo crear una clave asimétrica, guardarla en un contenedor de claves, recuperarla posteriormente y eliminarla del contenedor.</span><span class="sxs-lookup"><span data-stu-id="4fe41-116">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>  
  
 <span data-ttu-id="4fe41-117">Observe que el código de los métodos `GenKey_SaveInContainer` y `GetKeyFromContainer` es similar.</span><span class="sxs-lookup"><span data-stu-id="4fe41-117">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span>  <span data-ttu-id="4fe41-118">Si especifica el nombre de un contenedor de claves para un objeto <xref:System.Security.Cryptography.CspParameters> y lo pasa a un objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> con la propiedad <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> o la propiedad <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> establecidas en true, ocurre lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4fe41-118">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to true, the following occurs.</span></span>  <span data-ttu-id="4fe41-119">Si no existe un contenedor de claves con el nombre especificado, se crea uno y la clave se conserva.</span><span class="sxs-lookup"><span data-stu-id="4fe41-119">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>  <span data-ttu-id="4fe41-120">Si no existe un contenedor de claves con el nombre especificado, la clave del contenedor se carga automáticamente en el objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> actual.</span><span class="sxs-lookup"><span data-stu-id="4fe41-120">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>  <span data-ttu-id="4fe41-121">Por lo tanto, el código del método `GenKey_SaveInContainer` conserva la clave porque se ejecuta primero, mientras que el código del método `GetKeyFromContainer` carga la clave porque se ejecuta en segundo lugar.</span><span class="sxs-lookup"><span data-stu-id="4fe41-121">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it is run second.</span></span>  
  
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
Key added to container:  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key retrieved from container :  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key deleted.  
Key added to container:  
<RSAKeyValue> Key Information B</RSAKeyValue>  
Key deleted.  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fe41-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fe41-122">See also</span></span>

- [<span data-ttu-id="4fe41-123">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="4fe41-123">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)  
- [<span data-ttu-id="4fe41-124">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="4fe41-124">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)  
- [<span data-ttu-id="4fe41-125">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="4fe41-125">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)  
- [<span data-ttu-id="4fe41-126">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4fe41-126">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
