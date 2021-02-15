---
description: 'Más información sobre: Tutorial: cifrado y descifrado de cadenas en Visual Basic'
title: Cifrar y descifrar cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: afc1eeaec85b2e430aead7f16401289b6e2e9e49
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471089"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="d48e4-103">Tutorial: Cifrar y descifrar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d48e4-103">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>

<span data-ttu-id="d48e4-104">En este tutorial se muestra cómo usar la <xref:System.Security.Cryptography.DESCryptoServiceProvider> clase para cifrar y descifrar cadenas mediante la versión del proveedor de servicios criptográficos (CSP) del algoritmo Triple Data Encryption Standard ( <xref:System.Security.Cryptography.TripleDES> ).</span><span class="sxs-lookup"><span data-stu-id="d48e4-104">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="d48e4-105">El primer paso consiste en crear una clase contenedora simple que encapsule el algoritmo 3DES y almacene los datos cifrados como una cadena codificada en base 64.</span><span class="sxs-lookup"><span data-stu-id="d48e4-105">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="d48e4-106">A continuación, ese contenedor se usa para almacenar de forma segura los datos de usuario privados en un archivo de texto accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="d48e4-106">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="d48e4-107">Puede usar el cifrado para proteger los secretos del usuario (por ejemplo, contraseñas) y para que los usuarios no autorizados no puedan leer las credenciales.</span><span class="sxs-lookup"><span data-stu-id="d48e4-107">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="d48e4-108">Esto puede impedir que la identidad de un usuario autorizado se robe, lo que protege los recursos del usuario y proporciona sin repudio.</span><span class="sxs-lookup"><span data-stu-id="d48e4-108">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="d48e4-109">El cifrado también puede impedir que usuarios no autorizados tengan acceso a los datos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="d48e4-109">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="d48e4-110">Para más información, vea [Servicios criptográficos](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="d48e4-110">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d48e4-111">Los algoritmos de Rijndael (ahora denominados Estándar de cifrado avanzado [AES]) y del estándar de cifrado de datos triple (3DES) proporcionan una mayor seguridad que DES porque son más intensivo computacionalmente.</span><span class="sxs-lookup"><span data-stu-id="d48e4-111">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="d48e4-112">Para obtener más información, vea <xref:System.Security.Cryptography.DES> y <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="d48e4-112">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="d48e4-113">Para crear el contenedor de cifrado</span><span class="sxs-lookup"><span data-stu-id="d48e4-113">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="d48e4-114">Cree la `Simple3Des` clase para encapsular los métodos de cifrado y descifrado.</span><span class="sxs-lookup"><span data-stu-id="d48e4-114">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="d48e4-115">Agregue una importación del espacio de nombres Cryptography al inicio del archivo que contiene la `Simple3Des` clase.</span><span class="sxs-lookup"><span data-stu-id="d48e4-115">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="d48e4-116">En la `Simple3Des` clase, agregue un campo privado para almacenar el proveedor de servicios criptográficos de 3DES.</span><span class="sxs-lookup"><span data-stu-id="d48e4-116">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="d48e4-117">Agregue un método privado que cree una matriz de bytes de una longitud especificada a partir del hash de la clave especificada.</span><span class="sxs-lookup"><span data-stu-id="d48e4-117">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="d48e4-118">Agregue un constructor para inicializar el proveedor de servicios criptográficos de 3DES.</span><span class="sxs-lookup"><span data-stu-id="d48e4-118">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="d48e4-119">El `key` parámetro controla los `EncryptData` `DecryptData` métodos y.</span><span class="sxs-lookup"><span data-stu-id="d48e4-119">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="d48e4-120">Agregue un método público que cifre una cadena.</span><span class="sxs-lookup"><span data-stu-id="d48e4-120">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="d48e4-121">Agregue un método público que descifre una cadena.</span><span class="sxs-lookup"><span data-stu-id="d48e4-121">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="d48e4-122">La clase contenedora ahora se puede usar para proteger los recursos de usuario.</span><span class="sxs-lookup"><span data-stu-id="d48e4-122">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="d48e4-123">En este ejemplo, se usa para almacenar de forma segura los datos de usuario privados en un archivo de texto accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="d48e4-123">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="d48e4-124">Para probar el contenedor de cifrado</span><span class="sxs-lookup"><span data-stu-id="d48e4-124">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="d48e4-125">En una clase independiente, agregue un método que use el método del contenedor `EncryptData` para cifrar una cadena y escribirla en la carpeta Mis documentos del usuario.</span><span class="sxs-lookup"><span data-stu-id="d48e4-125">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="d48e4-126">Agregue un método que lea la cadena cifrada de la carpeta Mis documentos del usuario y descifre la cadena con el método del contenedor `DecryptData` .</span><span class="sxs-lookup"><span data-stu-id="d48e4-126">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="d48e4-127">Agregue el código de la interfaz de usuario para llamar a los `TestEncoding` `TestDecoding` métodos y.</span><span class="sxs-lookup"><span data-stu-id="d48e4-127">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="d48e4-128">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d48e4-128">Run the application.</span></span>  
  
     <span data-ttu-id="d48e4-129">Al probar la aplicación, tenga en cuenta que no descifrará los datos si proporciona una contraseña incorrecta.</span><span class="sxs-lookup"><span data-stu-id="d48e4-129">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48e4-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d48e4-130">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="d48e4-131">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="d48e4-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
