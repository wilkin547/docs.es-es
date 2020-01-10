---
title: 'Cómo: Utilizar la protección de datos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: 0efd677f11189b28b8efc184c04b30a047ab942b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706037"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="520dd-102">Cómo: Utilizar la protección de datos</span><span class="sxs-lookup"><span data-stu-id="520dd-102">How to: Use Data Protection</span></span>
<span data-ttu-id="520dd-103">.NET Framework proporciona acceso a la API de protección de datos (DPAPI), que permite cifrar datos usando la información del equipo o la cuenta del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="520dd-103">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="520dd-104">Cuando se usa la DPAPI, se alivia el difícil problema de generar y almacenar explícitamente una clave criptográfica.</span><span class="sxs-lookup"><span data-stu-id="520dd-104">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="520dd-105">Use la clase <xref:System.Security.Cryptography.ProtectedMemory> para cifrar una matriz de bytes en memoria.</span><span class="sxs-lookup"><span data-stu-id="520dd-105">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="520dd-106">Esta funcionalidad está disponible en Microsoft Windows XP y en los sistemas operativos posteriores.</span><span class="sxs-lookup"><span data-stu-id="520dd-106">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="520dd-107">Puede especificar que la memoria cifrada por el proceso actual pueda ser descifrada solo por el proceso actual, por todos los procesos o desde el mismo contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="520dd-107">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="520dd-108">Consulte la enumeración <xref:System.Security.Cryptography.MemoryProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedMemory>.</span><span class="sxs-lookup"><span data-stu-id="520dd-108">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="520dd-109">Use la clase <xref:System.Security.Cryptography.ProtectedData> para cifrar una copia de una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="520dd-109">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="520dd-110">Esta funcionalidad está disponible en Microsoft Windows 2000 y en los sistemas operativos posteriores.</span><span class="sxs-lookup"><span data-stu-id="520dd-110">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="520dd-111">Puede especificar que los datos cifrados por la cuenta de usuario actual solo puedan ser descifrados por la misma cuenta de usuario o que puedan ser descifrados por cualquier cuenta del equipo.</span><span class="sxs-lookup"><span data-stu-id="520dd-111">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="520dd-112">Consulte la enumeración <xref:System.Security.Cryptography.DataProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedData>.</span><span class="sxs-lookup"><span data-stu-id="520dd-112">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="520dd-113">Para cifrar los datos en memoria mediante la protección de datos</span><span class="sxs-lookup"><span data-stu-id="520dd-113">To encrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="520dd-114">Llame al método <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> estático mientras pasa la matriz de bytes que se vaya a cifrar, la entropía y el ámbito de la protección de memoria.</span><span class="sxs-lookup"><span data-stu-id="520dd-114">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="520dd-115">Para descifrar los datos en memoria mediante la protección de datos</span><span class="sxs-lookup"><span data-stu-id="520dd-115">To decrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="520dd-116">Llame al método <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> estático mientras pasa la matriz de bytes que se vaya a descifrar y el ámbito de la protección de memoria.</span><span class="sxs-lookup"><span data-stu-id="520dd-116">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="520dd-117">Para cifrar datos en un archivo o una secuencia usando la protección de datos</span><span class="sxs-lookup"><span data-stu-id="520dd-117">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="520dd-118">Cree una entropía aleatoria.</span><span class="sxs-lookup"><span data-stu-id="520dd-118">Create random entropy.</span></span>  
  
2. <span data-ttu-id="520dd-119">Llame al método <xref:System.Security.Cryptography.ProtectedData.Protect%2A> estático mientras pasa la matriz de bytes que se vaya a cifrar, la entropía y el ámbito de la protección de datos.</span><span class="sxs-lookup"><span data-stu-id="520dd-119">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="520dd-120">Escriba los datos cifrados en un archivo o en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="520dd-120">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="520dd-121">Para descifrar los datos de un archivo o secuencia usando la protección de datos</span><span class="sxs-lookup"><span data-stu-id="520dd-121">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="520dd-122">Lea los datos cifrados desde un archivo o una secuencia.</span><span class="sxs-lookup"><span data-stu-id="520dd-122">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="520dd-123">Llame al método <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> estático mientras pasa la matriz de bytes que se vaya a descifrar y el ámbito de la protección de datos.</span><span class="sxs-lookup"><span data-stu-id="520dd-123">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="520dd-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="520dd-124">Example</span></span>  
 <span data-ttu-id="520dd-125">En el siguiente ejemplo de código se muestran dos formas de cifrado y descifrado.</span><span class="sxs-lookup"><span data-stu-id="520dd-125">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="520dd-126">En primer lugar, el ejemplo de código cifra y luego descifra la matriz de bytes en memoria.</span><span class="sxs-lookup"><span data-stu-id="520dd-126">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="520dd-127">A continuación, el ejemplo de código cifra una copia de una matriz de bytes, la guarda en un archivo, vuelve a cargar los datos del archivo y, a continuación, descifra los datos.</span><span class="sxs-lookup"><span data-stu-id="520dd-127">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="520dd-128">El ejemplo muestra los datos originales, los datos cifrados y los datos descifrados.</span><span class="sxs-lookup"><span data-stu-id="520dd-128">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="520dd-129">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="520dd-129">Compiling the Code</span></span>  
  
- <span data-ttu-id="520dd-130">Incluya una referencia a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="520dd-130">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="520dd-131">Incluya el espacio de nombres <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> y <xref:System.Text>.</span><span class="sxs-lookup"><span data-stu-id="520dd-131">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="520dd-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="520dd-132">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
