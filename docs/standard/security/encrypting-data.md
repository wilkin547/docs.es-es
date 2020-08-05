---
title: Cifrar datos
description: Obtenga información sobre cómo cifrar datos en .NET mediante un algoritmo simétrico o asimétrico.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 8a8b5988a13ab571284b08c7aaece3542467aa71
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556974"
---
# <a name="encrypting-data"></a><span data-ttu-id="0beef-103">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="0beef-103">Encrypting Data</span></span>

<span data-ttu-id="0beef-104">El cifrado simétrico y el cifrado asimétrico se efectúan mediante procesos distintos.</span><span class="sxs-lookup"><span data-stu-id="0beef-104">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="0beef-105">El cifrado simétrico se realiza en secuencias y, por tanto, resulta útil para cifrar grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="0beef-105">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="0beef-106">El cifrado asimétrico se realiza en un pequeño número de bytes y, por tanto, solo resulta útil para pequeñas cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="0beef-106">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="0beef-107">Cifrado simétrico</span><span class="sxs-lookup"><span data-stu-id="0beef-107">Symmetric Encryption</span></span>  

<span data-ttu-id="0beef-108">Las clases de criptografía simétrica administrada se usan con una clase de secuencia especial llamada <xref:System.Security.Cryptography.CryptoStream> que cifra los datos leídos en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0beef-108">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="0beef-109">La clase **CryptoStream** se inicializa con una clase de secuencia administrada, una clase que implementa la <xref:System.Security.Cryptography.ICryptoTransform> interfaz (creada a partir de una clase que implementa un algoritmo criptográfico) y una <xref:System.Security.Cryptography.CryptoStreamMode> enumeración que describe el tipo de acceso permitido a **CryptoStream**.</span><span class="sxs-lookup"><span data-stu-id="0beef-109">The **CryptoStream** class is initialized with a managed stream class, a class that implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="0beef-110">La clase **CryptoStream** puede inicializarse usando cualquier clase que derive de la <xref:System.IO.Stream> clase, incluidas <xref:System.IO.FileStream> , <xref:System.IO.MemoryStream> y <xref:System.Net.Sockets.NetworkStream> .</span><span class="sxs-lookup"><span data-stu-id="0beef-110">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="0beef-111">Mediante estas clases, puede realizar el cifrado simétrico en diversos objetos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="0beef-111">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
<span data-ttu-id="0beef-112">En el ejemplo siguiente se muestra cómo crear una nueva instancia de la clase de implementación predeterminada para el <xref:System.Security.Cryptography.Aes> algoritmo.</span><span class="sxs-lookup"><span data-stu-id="0beef-112">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="0beef-113">La instancia de se usa para realizar el cifrado en una clase **CryptoStream** .</span><span class="sxs-lookup"><span data-stu-id="0beef-113">The instance is used to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="0beef-114">En este ejemplo, **CryptoStream** se inicializa con un objeto de secuencia llamado `myStream` que puede ser cualquier tipo de secuencia administrada.</span><span class="sxs-lookup"><span data-stu-id="0beef-114">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="0beef-115">Al método **CreateEncryptor** de la clase **AES** se le pasa la clave y el IV que se usan para el cifrado.</span><span class="sxs-lookup"><span data-stu-id="0beef-115">The **CreateEncryptor** method from the **Aes** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="0beef-116">En este caso, se usan la clave predeterminada y el IV generados desde `aes` .</span><span class="sxs-lookup"><span data-stu-id="0beef-116">In this case, the default key and IV generated from `aes` are used.</span></span>
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
<span data-ttu-id="0beef-117">Después de ejecutar este código, los datos escritos en el objeto **CryptoStream** se cifran mediante el algoritmo AES.</span><span class="sxs-lookup"><span data-stu-id="0beef-117">After this code is executed, any data written to the **CryptoStream** object is encrypted using the AES algorithm.</span></span>  
  
<span data-ttu-id="0beef-118">En el ejemplo siguiente se muestra todo el proceso de crear una secuencia, cifrarla, escribir en ella y cerrarla.</span><span class="sxs-lookup"><span data-stu-id="0beef-118">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="0beef-119">En este ejemplo se crea una secuencia de archivos que se cifra mediante la clase **CryptoStream** y la clase **AES** .</span><span class="sxs-lookup"><span data-stu-id="0beef-119">This example creates a file stream that is encrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="0beef-120">Se escribe un mensaje en la secuencia cifrada con la clase <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="0beef-120">A message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span>
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

<span data-ttu-id="0beef-121">El código cifra el flujo mediante el algoritmo simétrico AES y escribe "Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="0beef-121">The code encrypts the stream using the AES symmetric algorithm, and writes "Hello World!"</span></span> <span data-ttu-id="0beef-122">en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0beef-122">to the stream.</span></span> <span data-ttu-id="0beef-123">Si el código es correcto, crea un archivo cifrado denominado *TestData.txt* y muestra el texto siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="0beef-123">If the code is successful, it creates an encrypted file named *TestData.txt* and displays the following text to the console:</span></span>  
  
```console  
The text was encrypted.  
```  

<span data-ttu-id="0beef-124">Puede descifrar el archivo mediante el ejemplo de descifrado simétrico en [descifrar datos](decrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="0beef-124">You can decrypt the file by using the symmetric decryption example in [Decrypting Data](decrypting-data.md).</span></span> <span data-ttu-id="0beef-125">Este ejemplo y este ejemplo especifican la misma clave y el IV.</span><span class="sxs-lookup"><span data-stu-id="0beef-125">That example and this example specify the same key and IV.</span></span>

<span data-ttu-id="0beef-126">Sin embargo, si se produce una excepción, el código muestra el texto siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="0beef-126">However, if an exception is raised, the code displays the following text to the console:</span></span>  
  
```console  
The encryption failed.  
```

## <a name="asymmetric-encryption"></a><span data-ttu-id="0beef-127">Cifrado asimétrico</span><span class="sxs-lookup"><span data-stu-id="0beef-127">Asymmetric Encryption</span></span>

<span data-ttu-id="0beef-128">Los algoritmos asimétricos suelen usarse para cifrar pequeñas cantidades de datos, como el cifrado de una clave simétrica y un IV.</span><span class="sxs-lookup"><span data-stu-id="0beef-128">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="0beef-129">Normalmente, cuando se realiza un cifrado asimétrico, se usa la clave pública generada por terceros.</span><span class="sxs-lookup"><span data-stu-id="0beef-129">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="0beef-130"><xref:System.Security.Cryptography.RSA>.Net proporciona la clase para este propósito.</span><span class="sxs-lookup"><span data-stu-id="0beef-130">The <xref:System.Security.Cryptography.RSA> class is provided by .NET for this purpose.</span></span>  
  
<span data-ttu-id="0beef-131">En el ejemplo siguiente se usa la información de clave pública para cifrar una clave simétrica y un IV.</span><span class="sxs-lookup"><span data-stu-id="0beef-131">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="0beef-132">Se inicializan dos matrices de bytes que representan la clave pública de un tercero.</span><span class="sxs-lookup"><span data-stu-id="0beef-132">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="0beef-133">Se inicializa un objeto <xref:System.Security.Cryptography.RSAParameters> en estos valores.</span><span class="sxs-lookup"><span data-stu-id="0beef-133">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="0beef-134">Después, el objeto **RSAParameters** (junto con la clave pública que representa) se importa en una instancia de **RSA** mediante el <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="0beef-134">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSA** instance using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0beef-135">Por último, se cifran la clave privada y el IV creados por una <xref:System.Security.Cryptography.Aes> clase.</span><span class="sxs-lookup"><span data-stu-id="0beef-135">Finally, the private key and IV created by an <xref:System.Security.Cryptography.Aes> class are encrypted.</span></span> <span data-ttu-id="0beef-136">Este ejemplo requiere sistemas que tengan instalado el cifrado de 128 bits.</span><span class="sxs-lookup"><span data-stu-id="0beef-136">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System
Imports System.Security.Cryptography

Module Module1

    Sub Main()
        'Initialize the byte arrays to the public key information.  
        Dim modulus As Byte() = {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19, 202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}

        Dim exponent As Byte() = {1, 0, 1}

        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte
        Dim encryptedSymmetricIV() As Byte

        'Create a new instance of the default RSA implementation class.
        Dim rsa As RSA = RSA.Create()

        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()

        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus
        rsaKeyInfo.Exponent = exponent

        'Import key parameters into rsa
        rsa.ImportParameters(rsaKeyInfo)

        'Create a new instance of the default Aes implementation class.  
        Dim aes As Aes = Aes.Create()

        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1)
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1)
    End Sub

End Module
```  
  
```csharp  
using System;
using System.Security.Cryptography;

class Class1
{
    static void Main()
    {
        //Initialize the byte arrays to the public key information.  
        byte[] modulus = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};

        byte[] exponent = { 1, 0, 1 };

        //Create values to store encrypted symmetric keys.  
        byte[] encryptedSymmetricKey;
        byte[] encryptedSymmetricIV;

        //Create a new instance of the RSA class.  
        RSA rsa = RSA.Create();

        //Create a new instance of the RSAParameters structure.  
        RSAParameters rsaKeyInfo = new RSAParameters();

        //Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus;
        rsaKeyInfo.Exponent = exponent;

        //Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo);

        //Create a new instance of the default Aes implementation class.  
        Aes aes = Aes.Create();

        //Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1);
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="0beef-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0beef-137">See also</span></span>

- [<span data-ttu-id="0beef-138">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="0beef-138">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="0beef-139">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="0beef-139">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="0beef-140">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="0beef-140">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="0beef-141">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="0beef-141">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="0beef-142">Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno</span><span class="sxs-lookup"><span data-stu-id="0beef-142">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="0beef-143">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="0beef-143">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
