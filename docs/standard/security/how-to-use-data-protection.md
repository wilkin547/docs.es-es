---
title: Procedimiento para usar la protección de datos
description: Aprenda a usar la protección de datos mediante el acceso a la API de protección de datos (DPAPI) en .NET.
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
ms.openlocfilehash: c7f88105727dfd33c87a815054aa317ac2052e83
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598598"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="46c92-103">Procedimiento para usar la protección de datos</span><span class="sxs-lookup"><span data-stu-id="46c92-103">How to: Use Data Protection</span></span>
<span data-ttu-id="46c92-104">.NET Framework proporciona acceso a la API de protección de datos (DPAPI), que permite cifrar datos usando la información del equipo o la cuenta del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="46c92-104">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="46c92-105">Cuando se usa la DPAPI, se alivia el difícil problema de generar y almacenar explícitamente una clave criptográfica.</span><span class="sxs-lookup"><span data-stu-id="46c92-105">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="46c92-106">Use la clase <xref:System.Security.Cryptography.ProtectedMemory> para cifrar una matriz de bytes en memoria.</span><span class="sxs-lookup"><span data-stu-id="46c92-106">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="46c92-107">Esta funcionalidad está disponible en Microsoft Windows XP y en los sistemas operativos posteriores.</span><span class="sxs-lookup"><span data-stu-id="46c92-107">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="46c92-108">Puede especificar que la memoria cifrada por el proceso actual pueda ser descifrada solo por el proceso actual, por todos los procesos o desde el mismo contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="46c92-108">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="46c92-109">Consulte la enumeración <xref:System.Security.Cryptography.MemoryProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedMemory>.</span><span class="sxs-lookup"><span data-stu-id="46c92-109">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="46c92-110">Use la clase <xref:System.Security.Cryptography.ProtectedData> para cifrar una copia de una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="46c92-110">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="46c92-111">Esta funcionalidad está disponible en Microsoft Windows 2000 y en los sistemas operativos posteriores.</span><span class="sxs-lookup"><span data-stu-id="46c92-111">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="46c92-112">Puede especificar que los datos cifrados por la cuenta de usuario actual solo puedan ser descifrados por la misma cuenta de usuario o que puedan ser descifrados por cualquier cuenta del equipo.</span><span class="sxs-lookup"><span data-stu-id="46c92-112">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="46c92-113">Consulte la enumeración <xref:System.Security.Cryptography.DataProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedData>.</span><span class="sxs-lookup"><span data-stu-id="46c92-113">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="46c92-114">Para cifrar los datos en memoria mediante la protección de datos</span><span class="sxs-lookup"><span data-stu-id="46c92-114">To encrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="46c92-115">Llame al método <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> estático mientras pasa la matriz de bytes que se vaya a cifrar, la entropía y el ámbito de la protección de memoria.</span><span class="sxs-lookup"><span data-stu-id="46c92-115">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="46c92-116">Para descifrar los datos en memoria mediante la protección de datos</span><span class="sxs-lookup"><span data-stu-id="46c92-116">To decrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="46c92-117">Llame al método <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> estático mientras pasa la matriz de bytes que se vaya a descifrar y el ámbito de la protección de memoria.</span><span class="sxs-lookup"><span data-stu-id="46c92-117">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="46c92-118">Para cifrar datos en un archivo o una secuencia usando la protección de datos</span><span class="sxs-lookup"><span data-stu-id="46c92-118">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="46c92-119">Cree una entropía aleatoria.</span><span class="sxs-lookup"><span data-stu-id="46c92-119">Create random entropy.</span></span>  
  
2. <span data-ttu-id="46c92-120">Llame al método <xref:System.Security.Cryptography.ProtectedData.Protect%2A> estático mientras pasa la matriz de bytes que se vaya a cifrar, la entropía y el ámbito de la protección de datos.</span><span class="sxs-lookup"><span data-stu-id="46c92-120">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="46c92-121">Escriba los datos cifrados en un archivo o en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="46c92-121">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="46c92-122">Para descifrar los datos de un archivo o secuencia usando la protección de datos</span><span class="sxs-lookup"><span data-stu-id="46c92-122">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="46c92-123">Lea los datos cifrados desde un archivo o una secuencia.</span><span class="sxs-lookup"><span data-stu-id="46c92-123">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="46c92-124">Llame al método <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> estático mientras pasa la matriz de bytes que se vaya a descifrar y el ámbito de la protección de datos.</span><span class="sxs-lookup"><span data-stu-id="46c92-124">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46c92-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46c92-125">Example</span></span>  
 <span data-ttu-id="46c92-126">En el siguiente ejemplo de código se muestran dos formas de cifrado y descifrado.</span><span class="sxs-lookup"><span data-stu-id="46c92-126">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="46c92-127">En primer lugar, el ejemplo de código cifra y luego descifra la matriz de bytes en memoria.</span><span class="sxs-lookup"><span data-stu-id="46c92-127">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="46c92-128">A continuación, el ejemplo de código cifra una copia de una matriz de bytes, la guarda en un archivo, vuelve a cargar los datos del archivo y, a continuación, descifra los datos.</span><span class="sxs-lookup"><span data-stu-id="46c92-128">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="46c92-129">El ejemplo muestra los datos originales, los datos cifrados y los datos descifrados.</span><span class="sxs-lookup"><span data-stu-id="46c92-129">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46c92-130">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="46c92-130">Compiling the Code</span></span>  
  
- <span data-ttu-id="46c92-131">Incluya una referencia a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="46c92-131">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="46c92-132">Incluya el espacio de nombres <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> y <xref:System.Text>.</span><span class="sxs-lookup"><span data-stu-id="46c92-132">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c92-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="46c92-133">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
