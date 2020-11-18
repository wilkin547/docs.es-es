---
title: 'Cómo: almacenar claves asimétricas en un contenedor de claves'
description: Aprenda a almacenar claves asimétricas en un contenedor de claves en .NET. Vea cómo crear una clave asimétrica, guardarla en un contenedor de claves y recuperar y eliminar la clave.
ms.date: 05/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET]
- encryption [.NET], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: 946657f0c96aa80705575d8203ff158c63a72780
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820155"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="da174-104">Almacenar claves asimétricas en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="da174-104">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="da174-105">Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="da174-105">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="da174-106">Si necesita almacenar una clave privada, utilice un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="da174-106">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="da174-107">Para obtener más información acerca de los contenedores de claves, consulte Descripción de los [contenedores de claves RSA de nivel de equipo y de nivel de usuario](/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="da174-107">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="da174-108">El código de este artículo se aplica a Windows y usa las características que no están disponibles en .NET Core 2,2 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="da174-108">The code in this article applies to Windows and uses features not available in .NET Core 2.2 and earlier versions.</span></span> <span data-ttu-id="da174-109">Para obtener más información, consulte [dotnet/Runtime # 23391](https://github.com/dotnet/runtime/issues/23391).</span><span class="sxs-lookup"><span data-stu-id="da174-109">For more information, see [dotnet/runtime#23391](https://github.com/dotnet/runtime/issues/23391).</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="da174-110">Crear una clave asimétrica y guardarla en un contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="da174-110">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="da174-111">Cree una nueva instancia de una <xref:System.Security.Cryptography.CspParameters> clase y pase el nombre que desea que llame al contenedor de claves al <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.</span><span class="sxs-lookup"><span data-stu-id="da174-111">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="da174-112">Cree una nueva instancia de una clase que derive de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase (normalmente <xref:System.Security.Cryptography.RSACryptoServiceProvider> o <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) y pase el objeto creado previamente `CspParameters` a su constructor.</span><span class="sxs-lookup"><span data-stu-id="da174-112">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="da174-113">La creación y recuperación de una clave asimétrica es una operación.</span><span class="sxs-lookup"><span data-stu-id="da174-113">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="da174-114">Si una clave todavía no está en el contenedor, se crea antes de que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="da174-114">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="da174-115">Eliminar la clave del contenedor de claves</span><span class="sxs-lookup"><span data-stu-id="da174-115">Delete the key from the key container</span></span>

1. <span data-ttu-id="da174-116">Cree una nueva instancia de una `CspParameters` clase y pase el nombre que desea que llame al contenedor de claves al <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.</span><span class="sxs-lookup"><span data-stu-id="da174-116">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="da174-117">Cree una nueva instancia de una clase que derive de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase (normalmente `RSACryptoServiceProvider` o `DSACryptoServiceProvider` ) y pase el objeto creado previamente `CspParameters` a su constructor.</span><span class="sxs-lookup"><span data-stu-id="da174-117">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="da174-118">Establezca la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> propiedad o <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> de la clase que se deriva de `AsymmetricAlgorithm` en `false` ( `False` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="da174-118">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="da174-119">Llame al `Clear` método de la clase que deriva de `AsymmetricAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="da174-119">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="da174-120">Este método libera todos los recursos de la clase y borra el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="da174-120">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="da174-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da174-121">Example</span></span>

<span data-ttu-id="da174-122">En el ejemplo siguiente se muestra cómo crear una clave asimétrica, guardarla en un contenedor de claves, recuperarla posteriormente y eliminarla del contenedor.</span><span class="sxs-lookup"><span data-stu-id="da174-122">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="da174-123">Observe que el código de los métodos `GenKey_SaveInContainer` y `GetKeyFromContainer` es similar.</span><span class="sxs-lookup"><span data-stu-id="da174-123">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="da174-124">Cuando se especifica un nombre de contenedor de claves para un <xref:System.Security.Cryptography.CspParameters> objeto y se pasa a un <xref:System.Security.Cryptography.AsymmetricAlgorithm> objeto con la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> propiedad o la <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> propiedad establecida en `true` , el comportamiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="da174-124">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="da174-125">Si no existe un contenedor de claves con el nombre especificado, se crea uno y la clave se conserva.</span><span class="sxs-lookup"><span data-stu-id="da174-125">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="da174-126">Si no existe un contenedor de claves con el nombre especificado, la clave del contenedor se carga automáticamente en el objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> actual.</span><span class="sxs-lookup"><span data-stu-id="da174-126">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="da174-127">Por lo tanto, el código del `GenKey_SaveInContainer` método conserva la clave porque se ejecuta primero, mientras que el código del `GetKeyFromContainer` método carga la clave porque se ejecuta en segundo lugar.</span><span class="sxs-lookup"><span data-stu-id="da174-127">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

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

<span data-ttu-id="da174-128">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="da174-128">The output is as follows:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="da174-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="da174-129">See also</span></span>

- [<span data-ttu-id="da174-130">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="da174-130">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="da174-131">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="da174-131">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="da174-132">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="da174-132">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="da174-133">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="da174-133">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="da174-134">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="da174-134">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="da174-135">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="da174-135">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="da174-136">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="da174-136">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
