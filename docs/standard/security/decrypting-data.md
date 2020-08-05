---
title: Descifrar datos
description: Obtenga información acerca de cómo descifrar datos en .NET mediante un algoritmo simétrico o asimétrico.
ms.date: 07/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 2ba4c3ba43d688aeb66c67ec3f94f4a503d47892
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556987"
---
# <a name="decrypting-data"></a><span data-ttu-id="dc286-103">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="dc286-103">Decrypting Data</span></span>

<span data-ttu-id="dc286-104">El descifrado es la operación inversa del cifrado.</span><span class="sxs-lookup"><span data-stu-id="dc286-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="dc286-105">Para el cifrado de clave secreta, debe conocer la clave y el IV que se usaron para cifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="dc286-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="dc286-106">Para el cifrado de clave pública, debe conocer la clave pública (si los datos se cifraron mediante la clave privada) o la clave privada (si los datos se cifran mediante la clave pública).</span><span class="sxs-lookup"><span data-stu-id="dc286-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="dc286-107">Descifrado simétrico</span><span class="sxs-lookup"><span data-stu-id="dc286-107">Symmetric Decryption</span></span>

<span data-ttu-id="dc286-108">El descifrado de los datos cifrados con algoritmos simétricos es similar al proceso usado para cifrar datos con algoritmos simétricos.</span><span class="sxs-lookup"><span data-stu-id="dc286-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="dc286-109">La <xref:System.Security.Cryptography.CryptoStream> clase se usa con las clases de criptografía simétricas proporcionadas por .net para descifrar los datos leídos de cualquier objeto de secuencia administrado.</span><span class="sxs-lookup"><span data-stu-id="dc286-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="dc286-110">En el ejemplo siguiente se muestra cómo crear una nueva instancia de la clase de implementación predeterminada para el <xref:System.Security.Cryptography.Aes> algoritmo.</span><span class="sxs-lookup"><span data-stu-id="dc286-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="dc286-111">La instancia se utiliza para realizar el descifrado en un <xref:System.Security.Cryptography.CryptoStream> objeto.</span><span class="sxs-lookup"><span data-stu-id="dc286-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="dc286-112">En primer lugar, en este ejemplo se crea una nueva instancia de la clase de implementación de **AES** .</span><span class="sxs-lookup"><span data-stu-id="dc286-112">This example first creates a new instance of the **Aes** implementation class.</span></span> <span data-ttu-id="dc286-113">A continuación, se crea un objeto **CryptoStream** y se inicializa con el valor de una secuencia administrada llamada `myStream`.</span><span class="sxs-lookup"><span data-stu-id="dc286-113">Next it creates a **CryptoStream** object and initializes it to the value of a managed stream called `myStream`.</span></span> <span data-ttu-id="dc286-114">A continuación, se pasa al método **CreateDecryptor** de la clase **AES** la misma clave y el IV que se usaron para el cifrado y, a continuación, se pasa al constructor **CryptoStream** .</span><span class="sxs-lookup"><span data-stu-id="dc286-114">Next, the **CreateDecryptor** method from the **Aes** class is passed the same key and IV that was used for encryption and is then passed to the **CryptoStream** constructor.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="dc286-115">En el ejemplo siguiente se muestra todo el proceso de crear una secuencia, descifrarla, leer en ella y cerrarla.</span><span class="sxs-lookup"><span data-stu-id="dc286-115">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="dc286-116">Se crea un objeto de secuencia de archivos que lee un archivo denominado *TestData.txt*.</span><span class="sxs-lookup"><span data-stu-id="dc286-116">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="dc286-117">A continuación, el flujo de archivo se descifra con la clase **CryptoStream** y la clase **AES** .</span><span class="sxs-lookup"><span data-stu-id="dc286-117">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="dc286-118">En este ejemplo se especifican los valores de clave y IV que se usan en el ejemplo de cifrado simétrico para [cifrar datos](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="dc286-118">This example specifies key and IV values that are used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="dc286-119">No se muestra el código necesario para cifrar y transferir estos valores.</span><span class="sxs-lookup"><span data-stu-id="dc286-119">It does not show the code needed to encrypt and transfer these values.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Security.Cryptography

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Create a file stream.
            Dim myStream As FileStream = new FileStream("TestData.txt", FileMode.Open)

            'Create a new instance of the default Aes implementation class
            'and decrypt the stream.
            Dim aes As Aes = Aes.Create()

            'Create an instance of the CryptoStream class, pass it the file stream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            myStream.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The decryption Failed.")
            Throw
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

class Class1
{
    static void Main(string[] args)
    {
        //The key and IV must be the same values that were used
        //to encrypt the stream.
        byte[] key = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        byte[] iv = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        try
        {
            //Create a file stream.
            FileStream myStream = new FileStream("TestData.txt", FileMode.Open);

            //Create a new instance of the default Aes implementation class
            Aes aes = Aes.Create();

            //Create a CryptoStream, pass it the file stream, and decrypt
            //it with the Aes class using the key and IV.
            CryptoStream cryptStream = new CryptoStream(
               myStream,
               aes.CreateDecryptor(key, iv),
               CryptoStreamMode.Read);

            //Read the stream.
            StreamReader sReader = new StreamReader(cryptStream);

            //Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

            //Close the streams.
            sReader.Close();
            myStream.Close();
        }
        //Catch any exceptions.
        catch
        {
            Console.WriteLine("The decryption failed.");
            throw;
        }
    }
}
```

<span data-ttu-id="dc286-120">En el ejemplo anterior se utiliza la misma clave, el IV y el algoritmo utilizados en el ejemplo de cifrado simétrico para [cifrar datos](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="dc286-120">The preceding example uses the same key, IV, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="dc286-121">Descifra el archivo de *TestData.txt* que se crea en ese ejemplo y muestra el texto original en la consola.</span><span class="sxs-lookup"><span data-stu-id="dc286-121">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="dc286-122">Descifrado asimétrico</span><span class="sxs-lookup"><span data-stu-id="dc286-122">Asymmetric Decryption</span></span>

<span data-ttu-id="dc286-123">Normalmente, una parte (parte A) genera tanto una clave pública como privada y la almacena en memoria o en un contenedor de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="dc286-123">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="dc286-124">A continuación, la parte A envía la clave pública a otra parte (parte B).</span><span class="sxs-lookup"><span data-stu-id="dc286-124">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="dc286-125">Mediante el uso de la clave pública, la parte B cifra los datos y envía los datos de vuelta a la entidad A. Después de recibir los datos, la parte A los descifra mediante la clave privada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dc286-125">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="dc286-126">El descifrado será correcto solo si la parte A usa la clave privada que corresponde a la clave pública que la parte B usó para cifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="dc286-126">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="dc286-127">Para obtener información sobre cómo almacenar una clave asimétrica en un contenedor de claves criptográficas seguro y cómo recuperar posteriormente la clave asimétrica, consulte [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="dc286-127">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="dc286-128">En el ejemplo siguiente se muestra el descifrado de dos matrices de bytes que representan una clave simétrica y un IV.</span><span class="sxs-lookup"><span data-stu-id="dc286-128">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="dc286-129">Para obtener información sobre cómo extraer la clave pública asimétrica del objeto <xref:System.Security.Cryptography.RSA> en un formato que se pueda enviar fácilmente a un tercero, consulte [Encrypting Data](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="dc286-129">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a><span data-ttu-id="dc286-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc286-130">See also</span></span>

- [<span data-ttu-id="dc286-131">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="dc286-131">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="dc286-132">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="dc286-132">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="dc286-133">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="dc286-133">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="dc286-134">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="dc286-134">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="dc286-135">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="dc286-135">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="dc286-136">Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno</span><span class="sxs-lookup"><span data-stu-id="dc286-136">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="dc286-137">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="dc286-137">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
