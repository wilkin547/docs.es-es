---
title: 'Cómo: almacenar claves asimétricas en un contenedor de claves'
ms.date: 05/26/2020
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
ms.openlocfilehash: 36bae05fbfb35dc112e0c543c9a1a975a8fa8db5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143626"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="fbb73-102">Almacenar claves asimétricas en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="fbb73-102">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="fbb73-103">Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="fbb73-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="fbb73-104">Si necesita almacenar una clave privada, utilice un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="fbb73-104">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="fbb73-105">Para obtener más información acerca de los contenedores de claves, consulte Descripción de los [contenedores de claves RSA de nivel de equipo y de nivel de usuario](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fbb73-105">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="fbb73-106">Crear una clave asimétrica y guardarla en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="fbb73-106">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="fbb73-107">Cree una nueva instancia de una <xref:System.Security.Cryptography.CspParameters> clase y pase el nombre que desea que llame al contenedor de claves al <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.</span><span class="sxs-lookup"><span data-stu-id="fbb73-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="fbb73-108">Cree una nueva instancia de una clase que derive de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase (normalmente <xref:System.Security.Cryptography.RSACryptoServiceProvider> o <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) y pase el objeto creado previamente `CspParameters` a su constructor.</span><span class="sxs-lookup"><span data-stu-id="fbb73-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="fbb73-109">La creación y recuperación de una clave asimétrica es una operación.</span><span class="sxs-lookup"><span data-stu-id="fbb73-109">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="fbb73-110">Si una clave todavía no está en el contenedor, se crea antes de que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="fbb73-110">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="fbb73-111">Eliminar la clave del contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="fbb73-111">Delete the key from the key container</span></span>

1. <span data-ttu-id="fbb73-112">Cree una nueva instancia de una `CspParameters` clase y pase el nombre que desea que llame al contenedor de claves al <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.</span><span class="sxs-lookup"><span data-stu-id="fbb73-112">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="fbb73-113">Cree una nueva instancia de una clase que derive de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase (normalmente `RSACryptoServiceProvider` o `DSACryptoServiceProvider` ) y pase el objeto creado previamente `CspParameters` a su constructor.</span><span class="sxs-lookup"><span data-stu-id="fbb73-113">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="fbb73-114">Establezca la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> propiedad o <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> de la clase que se deriva de `AsymmetricAlgorithm` en `false` ( `False` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fbb73-114">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="fbb73-115">Llame al `Clear` método de la clase que deriva de `AsymmetricAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="fbb73-115">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="fbb73-116">Este método libera todos los recursos de la clase y borra el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="fbb73-116">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="fbb73-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbb73-117">Example</span></span>

<span data-ttu-id="fbb73-118">En el ejemplo siguiente se muestra cómo crear una clave asimétrica, guardarla en un contenedor de claves, recuperarla posteriormente y eliminarla del contenedor.</span><span class="sxs-lookup"><span data-stu-id="fbb73-118">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="fbb73-119">Observe que el código de los métodos `GenKey_SaveInContainer` y `GetKeyFromContainer` es similar.</span><span class="sxs-lookup"><span data-stu-id="fbb73-119">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="fbb73-120">Cuando se especifica un nombre de contenedor de claves para un <xref:System.Security.Cryptography.CspParameters> objeto y se pasa a un <xref:System.Security.Cryptography.AsymmetricAlgorithm> objeto con la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> propiedad o la <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> propiedad establecida en `true` , el comportamiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="fbb73-120">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="fbb73-121">Si no existe un contenedor de claves con el nombre especificado, se crea uno y la clave se conserva.</span><span class="sxs-lookup"><span data-stu-id="fbb73-121">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="fbb73-122">Si no existe un contenedor de claves con el nombre especificado, la clave del contenedor se carga automáticamente en el objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> actual.</span><span class="sxs-lookup"><span data-stu-id="fbb73-122">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="fbb73-123">Por lo tanto, el código del `GenKey_SaveInContainer` método conserva la clave porque se ejecuta primero, mientras que el código del `GetKeyFromContainer` método carga la clave porque se ejecuta en segundo lugar.</span><span class="sxs-lookup"><span data-stu-id="fbb73-123">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

```vb
Imports System
Imports System.Security.Cryptography

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

    Private Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key added to container:  {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub GetKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key retrieved from container : {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container.
        ' Delete the key entry in the container.
        Dim rsa As New RSACryptoServiceProvider(parameters) With {
            .PersistKeyInCsp = False
        }

        ' Call Clear to release resources and delete the key from the container.
        rsa.Clear()

        Console.WriteLine("Key deleted.")
    End Sub
End Class
```

```csharp
using System;
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
        catch (CryptographicException e)
        {
            Console.WriteLine(e.Message);
        }
    }

    private static void GenKey_SaveInContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key added to container: \n  {rsa.ToXmlString(true)}");
    }

    private static void GetKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key retrieved from container : \n {rsa.ToXmlString(true)}");
    }

    private static void DeleteKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container.
        using var rsa = new RSACryptoServiceProvider(parameters)
        {
            // Delete the key entry in the container.
            PersistKeyInCsp = false
        };

        // Call Clear to release resources and delete the key from the container.
        rsa.Clear();

        Console.WriteLine("Key deleted.");
    }
}
```

<span data-ttu-id="fbb73-124">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="fbb73-124">The output is as follows:</span></span>

```console
Key added to container:
<RSAKeyValue> Key Information A</RSAKeyValue>
Key retrieved from container :
<RSAKeyValue> Key Information A</RSAKeyValue>
Key deleted.
Key added to container:
<RSAKeyValue> Key Information B</RSAKeyValue>
Key deleted.
```

## <a name="see-also"></a><span data-ttu-id="fbb73-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbb73-125">See also</span></span>

- [<span data-ttu-id="fbb73-126">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="fbb73-126">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="fbb73-127">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="fbb73-127">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="fbb73-128">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="fbb73-128">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="fbb73-129">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="fbb73-129">Cryptographic services</span></span>](cryptographic-services.md)
