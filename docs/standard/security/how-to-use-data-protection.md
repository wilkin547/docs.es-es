---
title: Procedimiento para usar la protección de datos
description: Aprenda a usar la protección de datos mediante el acceso a la API de protección de datos (DPAPI) en .NET.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: ed1b18e2c6456b53559e8fb7e989f148fefd35c7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820103"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="97fd1-103">Procedimiento para usar la protección de datos</span><span class="sxs-lookup"><span data-stu-id="97fd1-103">How to: Use Data Protection</span></span>

> [!NOTE]
> <span data-ttu-id="97fd1-104">Este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="97fd1-104">This article applies to Windows.</span></span>
>
> <span data-ttu-id="97fd1-105">Para obtener información sobre ASP.NET Core, consulte [ASP.net Core protección de datos](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="97fd1-105">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="97fd1-106">.NET proporciona acceso a la API de protección de datos (DPAPI), que permite cifrar los datos con la información de la cuenta de usuario o el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="97fd1-106">.NET provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="97fd1-107">Cuando se usa la DPAPI, se alivia el difícil problema de generar y almacenar explícitamente una clave criptográfica.</span><span class="sxs-lookup"><span data-stu-id="97fd1-107">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
<span data-ttu-id="97fd1-108">Use la clase <xref:System.Security.Cryptography.ProtectedData> para cifrar una copia de una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="97fd1-108">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="97fd1-109">Esta funcionalidad está disponible en .NET Framework, .NET Core y .NET 5.</span><span class="sxs-lookup"><span data-stu-id="97fd1-109">This functionality is available in .NET Framework, .NET Core, and .NET 5.</span></span>  <span data-ttu-id="97fd1-110">Puede especificar que los datos cifrados por la cuenta de usuario actual solo puedan ser descifrados por la misma cuenta de usuario o que puedan ser descifrados por cualquier cuenta del equipo.</span><span class="sxs-lookup"><span data-stu-id="97fd1-110">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="97fd1-111">Consulte la enumeración <xref:System.Security.Cryptography.DataProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedData>.</span><span class="sxs-lookup"><span data-stu-id="97fd1-111">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
## <a name="encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="97fd1-112">Cifrado de datos en un archivo o una secuencia mediante la protección de datos</span><span class="sxs-lookup"><span data-stu-id="97fd1-112">Encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="97fd1-113">Cree una entropía aleatoria.</span><span class="sxs-lookup"><span data-stu-id="97fd1-113">Create random entropy.</span></span>  
  
2. <span data-ttu-id="97fd1-114">Llame al método <xref:System.Security.Cryptography.ProtectedData.Protect%2A> estático mientras pasa la matriz de bytes que se vaya a cifrar, la entropía y el ámbito de la protección de datos.</span><span class="sxs-lookup"><span data-stu-id="97fd1-114">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="97fd1-115">Escriba los datos cifrados en un archivo o en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="97fd1-115">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="97fd1-116">Para descifrar los datos de un archivo o secuencia usando la protección de datos</span><span class="sxs-lookup"><span data-stu-id="97fd1-116">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="97fd1-117">Lea los datos cifrados desde un archivo o una secuencia.</span><span class="sxs-lookup"><span data-stu-id="97fd1-117">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="97fd1-118">Llame al método <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> estático mientras pasa la matriz de bytes que se vaya a descifrar y el ámbito de la protección de datos.</span><span class="sxs-lookup"><span data-stu-id="97fd1-118">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97fd1-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97fd1-119">Example</span></span>

<span data-ttu-id="97fd1-120">En el siguiente ejemplo de código se muestran dos formas de cifrado y descifrado.</span><span class="sxs-lookup"><span data-stu-id="97fd1-120">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="97fd1-121">En primer lugar, el ejemplo de código cifra y luego descifra la matriz de bytes en memoria.</span><span class="sxs-lookup"><span data-stu-id="97fd1-121">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="97fd1-122">A continuación, el ejemplo de código cifra una copia de una matriz de bytes, la guarda en un archivo, vuelve a cargar los datos del archivo y, a continuación, descifra los datos.</span><span class="sxs-lookup"><span data-stu-id="97fd1-122">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="97fd1-123">El ejemplo muestra los datos originales, los datos cifrados y los datos descifrados.</span><span class="sxs-lookup"><span data-stu-id="97fd1-123">The example displays the original data, the encrypted data, and the decrypted data.</span></span>

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97fd1-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="97fd1-124">Compiling the Code</span></span>  

<span data-ttu-id="97fd1-125">Este ejemplo se compila y se ejecuta solo cuando el destino es .NET Framework y se ejecuta en Windows.</span><span class="sxs-lookup"><span data-stu-id="97fd1-125">This example compiles and runs only when targeting .NET Framework and running on Windows.</span></span>

- <span data-ttu-id="97fd1-126">Incluya una referencia a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="97fd1-126">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="97fd1-127">Incluya el espacio de nombres <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> y <xref:System.Text>.</span><span class="sxs-lookup"><span data-stu-id="97fd1-127">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97fd1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="97fd1-128">See also</span></span>

- [<span data-ttu-id="97fd1-129">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="97fd1-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="97fd1-130">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="97fd1-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="97fd1-131">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="97fd1-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [<span data-ttu-id="97fd1-132">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="97fd1-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
