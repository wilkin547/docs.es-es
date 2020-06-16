---
title: 'Cómo: almacenar claves asimétricas en un contenedor de claves'
description: Aprenda a almacenar claves asimétricas en un contenedor de claves en .NET. Vea cómo crear una clave asimétrica, guardarla en un contenedor de claves y recuperar y eliminar la clave.
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
ms.openlocfilehash: a0fbde37491043cc1aab71e9733087bf410b997d
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769034"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a>Almacenar claves asimétricas en un contenedor de claves

Las claves privadas asimétricas nunca deben almacenarse literalmente o en texto sin formato en el equipo local. Si necesita almacenar una clave privada, utilice un contenedor de claves. Para obtener más información acerca de los contenedores de claves, consulte Descripción de los [contenedores de claves RSA de nivel de equipo y de nivel de usuario](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a>Crear una clave asimétrica y guardarla en un contenedor de claves

1. Cree una nueva instancia de una <xref:System.Security.Cryptography.CspParameters> clase y pase el nombre que desea que llame al contenedor de claves al <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.

1. Cree una nueva instancia de una clase que derive de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase (normalmente <xref:System.Security.Cryptography.RSACryptoServiceProvider> o <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) y pase el objeto creado previamente `CspParameters` a su constructor.

> [!NOTE]
> La creación y recuperación de una clave asimétrica es una operación. Si una clave todavía no está en el contenedor, se crea antes de que se devuelva.
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a>Eliminar la clave del contenedor de claves

1. Cree una nueva instancia de una `CspParameters` clase y pase el nombre que desea que llame al contenedor de claves al <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> campo.

1. Cree una nueva instancia de una clase que derive de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase (normalmente `RSACryptoServiceProvider` o `DSACryptoServiceProvider` ) y pase el objeto creado previamente `CspParameters` a su constructor.

1. Establezca la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> propiedad o <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> de la clase que se deriva de `AsymmetricAlgorithm` en `false` ( `False` en Visual Basic).

1. Llame al `Clear` método de la clase que deriva de `AsymmetricAlgorithm` . Este método libera todos los recursos de la clase y borra el contenedor de claves.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo crear una clave asimétrica, guardarla en un contenedor de claves, recuperarla posteriormente y eliminarla del contenedor.

Observe que el código de los métodos `GenKey_SaveInContainer` y `GetKeyFromContainer` es similar. Cuando se especifica un nombre de contenedor de claves para un <xref:System.Security.Cryptography.CspParameters> objeto y se pasa a un <xref:System.Security.Cryptography.AsymmetricAlgorithm> objeto con la <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> propiedad o la <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> propiedad establecida en `true` , el comportamiento es el siguiente:

- Si no existe un contenedor de claves con el nombre especificado, se crea uno y la clave se conserva.
- Si no existe un contenedor de claves con el nombre especificado, la clave del contenedor se carga automáticamente en el objeto <xref:System.Security.Cryptography.AsymmetricAlgorithm> actual.

Por lo tanto, el código del `GenKey_SaveInContainer` método conserva la clave porque se ejecuta primero, mientras que el código del `GetKeyFromContainer` método carga la clave porque se ejecuta en segundo lugar.

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

La salida es como sigue:

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

## <a name="see-also"></a>Consulte también

- [Generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md)
- [Cifrar datos](encrypting-data.md)
- [Descifrar datos](decrypting-data.md)
- [Servicios criptográficos](cryptographic-services.md)
