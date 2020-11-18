---
title: Descifrar datos
description: Obtenga información acerca de cómo descifrar datos en .NET mediante un algoritmo simétrico o asimétrico.
ms.date: 07/16/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: cf286eeca8a9372c6532c56701e4775d5e09d786
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831109"
---
# <a name="decrypting-data"></a><span data-ttu-id="ae3be-103">Descifrar datos</span><span class="sxs-lookup"><span data-stu-id="ae3be-103">Decrypting Data</span></span>

<span data-ttu-id="ae3be-104">El descifrado es la operación inversa del cifrado.</span><span class="sxs-lookup"><span data-stu-id="ae3be-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="ae3be-105">Para el cifrado de clave secreta, debe conocer la clave y el IV que se usaron para cifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="ae3be-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="ae3be-106">Para el cifrado de clave pública, debe conocer la clave pública (si los datos se cifraron mediante la clave privada) o la clave privada (si los datos se cifran mediante la clave pública).</span><span class="sxs-lookup"><span data-stu-id="ae3be-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="ae3be-107">Descifrado simétrico</span><span class="sxs-lookup"><span data-stu-id="ae3be-107">Symmetric Decryption</span></span>

<span data-ttu-id="ae3be-108">El descifrado de los datos cifrados con algoritmos simétricos es similar al proceso usado para cifrar datos con algoritmos simétricos.</span><span class="sxs-lookup"><span data-stu-id="ae3be-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="ae3be-109">La <xref:System.Security.Cryptography.CryptoStream> clase se usa con las clases de criptografía simétricas proporcionadas por .net para descifrar los datos leídos de cualquier objeto de secuencia administrado.</span><span class="sxs-lookup"><span data-stu-id="ae3be-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="ae3be-110">En el ejemplo siguiente se muestra cómo crear una nueva instancia de la clase de implementación predeterminada para el <xref:System.Security.Cryptography.Aes> algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ae3be-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="ae3be-111">La instancia se utiliza para realizar el descifrado en un <xref:System.Security.Cryptography.CryptoStream> objeto.</span><span class="sxs-lookup"><span data-stu-id="ae3be-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="ae3be-112">En primer lugar, en este ejemplo se crea una nueva instancia de la <xref:System.Security.Cryptography.Aes> clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="ae3be-112">This example first creates a new instance of the <xref:System.Security.Cryptography.Aes> implementation class.</span></span> <span data-ttu-id="ae3be-113">Lee el valor del vector de inicialización (IV) de una variable de secuencia administrada, `myStream` .</span><span class="sxs-lookup"><span data-stu-id="ae3be-113">It reads the initialization vector (IV) value from a managed stream variable, `myStream`.</span></span> <span data-ttu-id="ae3be-114">A continuación, se crea una instancia <xref:System.Security.Cryptography.CryptoStream> de un objeto y se inicializa en el valor de la `myStream` instancia.</span><span class="sxs-lookup"><span data-stu-id="ae3be-114">Next it instantiates a <xref:System.Security.Cryptography.CryptoStream> object and initializes it to the value of the `myStream` instance.</span></span> <span data-ttu-id="ae3be-115">Al <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> método de la <xref:System.Security.Cryptography.Aes> instancia se le pasa el valor de IV y la misma clave que se usó para el cifrado.</span><span class="sxs-lookup"><span data-stu-id="ae3be-115">The <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> method from the <xref:System.Security.Cryptography.Aes> instance is passed the IV value and the same key that was used for encryption.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="ae3be-116">En el ejemplo siguiente se muestra todo el proceso de crear una secuencia, descifrarla, leer en ella y cerrarla.</span><span class="sxs-lookup"><span data-stu-id="ae3be-116">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="ae3be-117">Se crea un objeto de secuencia de archivos que lee un archivo denominado *TestData.txt*.</span><span class="sxs-lookup"><span data-stu-id="ae3be-117">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="ae3be-118">A continuación, el flujo de archivo se descifra con la clase **CryptoStream** y la clase **AES** .</span><span class="sxs-lookup"><span data-stu-id="ae3be-118">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="ae3be-119">En este ejemplo se especifica el valor de clave que se usa en el ejemplo de cifrado simétrico para [cifrar datos](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae3be-119">This example specifies key value that is used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="ae3be-120">No se muestra el código necesario para cifrar y transferir estos valores.</span><span class="sxs-lookup"><span data-stu-id="ae3be-120">It does not show the code needed to encrypt and transfer these values.</span></span>

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

<span data-ttu-id="ae3be-121">En el ejemplo anterior se utiliza la misma clave y el algoritmo utilizado en el ejemplo de cifrado simétrico para [cifrar datos](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae3be-121">The preceding example uses the same key, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="ae3be-122">Descifra el archivo de *TestData.txt* que se crea en ese ejemplo y muestra el texto original en la consola.</span><span class="sxs-lookup"><span data-stu-id="ae3be-122">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="ae3be-123">Descifrado asimétrico</span><span class="sxs-lookup"><span data-stu-id="ae3be-123">Asymmetric Decryption</span></span>

<span data-ttu-id="ae3be-124">Normalmente, una parte (parte A) genera tanto una clave pública como privada y la almacena en memoria o en un contenedor de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="ae3be-124">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="ae3be-125">A continuación, la parte A envía la clave pública a otra parte (parte B).</span><span class="sxs-lookup"><span data-stu-id="ae3be-125">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="ae3be-126">Mediante el uso de la clave pública, la parte B cifra los datos y envía los datos de vuelta a la entidad A. Después de recibir los datos, la parte A los descifra mediante la clave privada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ae3be-126">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="ae3be-127">El descifrado será correcto solo si la parte A usa la clave privada que corresponde a la clave pública que la parte B usó para cifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="ae3be-127">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="ae3be-128">Para obtener información sobre cómo almacenar una clave asimétrica en un contenedor de claves criptográficas seguro y cómo recuperar posteriormente la clave asimétrica, consulte [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="ae3be-128">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="ae3be-129">En el ejemplo siguiente se muestra el descifrado de dos matrices de bytes que representan una clave simétrica y un IV.</span><span class="sxs-lookup"><span data-stu-id="ae3be-129">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="ae3be-130">Para obtener información sobre cómo extraer la clave pública asimétrica del objeto <xref:System.Security.Cryptography.RSA> en un formato que se pueda enviar fácilmente a un tercero, consulte [Encrypting Data](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae3be-130">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ae3be-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae3be-131">See also</span></span>

- [<span data-ttu-id="ae3be-132">Generar claves para cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="ae3be-132">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="ae3be-133">Cifrar datos</span><span class="sxs-lookup"><span data-stu-id="ae3be-133">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="ae3be-134">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="ae3be-134">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="ae3be-135">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="ae3be-135">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="ae3be-136">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="ae3be-136">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="ae3be-137">Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno</span><span class="sxs-lookup"><span data-stu-id="ae3be-137">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="ae3be-138">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="ae3be-138">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
