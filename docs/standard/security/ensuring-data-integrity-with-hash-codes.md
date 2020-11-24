---
title: Asegurar la integridad de los datos mediante códigos hash
description: Obtenga información sobre cómo garantizar la integridad de los datos mediante códigos hash en .NET. Un valor hash es un valor numérico de longitud fija que solo identifica datos.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET], hash
- data integrity
- checking hash codes
- encryption [.NET], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 7f5e1d54efa3a5ccf28f2e0863a9bc9ccb80f894
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689750"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="6f88e-104">Asegurar la integridad de los datos mediante códigos hash</span><span class="sxs-lookup"><span data-stu-id="6f88e-104">Ensuring Data Integrity with Hash Codes</span></span>

<span data-ttu-id="6f88e-105">Un valor hash es un valor numérico de longitud fija que solo identifica datos.</span><span class="sxs-lookup"><span data-stu-id="6f88e-105">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="6f88e-106">Los valores hash representan grandes cantidades de datos como valores numéricos mucho menores, por lo que se usan con firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="6f88e-106">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="6f88e-107">Puede firmar un valor hash de forma más eficaz que un valor mayor.</span><span class="sxs-lookup"><span data-stu-id="6f88e-107">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="6f88e-108">Los valores hash también son útiles para comprobar la integridad de datos enviados a través de canales no seguros.</span><span class="sxs-lookup"><span data-stu-id="6f88e-108">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="6f88e-109">El valor hash de los datos recibidos puede compararse con el valor hash de los datos porque se envió para determinar si se alteraron los datos.</span><span class="sxs-lookup"><span data-stu-id="6f88e-109">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
<span data-ttu-id="6f88e-110">En este tema, se describe cómo generar y comprobar códigos hash mediante las clases en el espacio de nombres <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="6f88e-110">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="6f88e-111">Generar un valor hash</span><span class="sxs-lookup"><span data-stu-id="6f88e-111">Generating a Hash</span></span>

 <span data-ttu-id="6f88e-112">Las clases hash administradas pueden aplicar un valor hash a una matriz de bytes o a un objeto de secuencia administrado.</span><span class="sxs-lookup"><span data-stu-id="6f88e-112">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="6f88e-113">En el ejemplo siguiente, se utiliza el algoritmo hash SHA1 para crear un valor hash para una cadena.</span><span class="sxs-lookup"><span data-stu-id="6f88e-113">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="6f88e-114">El ejemplo utiliza la clase <xref:System.Text.UnicodeEncoding> para convertir la cadena en una matriz de bytes que aplica un valor hash mediante el uso de la clase <xref:System.Security.Cryptography.SHA256>.</span><span class="sxs-lookup"><span data-stu-id="6f88e-114">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA256> class.</span></span> <span data-ttu-id="6f88e-115">Posteriormente el valor hash se muestra en la consola.</span><span class="sxs-lookup"><span data-stu-id="6f88e-115">The hash value is then displayed to the console.</span></span>  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="6f88e-116">Este código mostrará la cadena siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="6f88e-116">This code will display the following string to the console:</span></span>  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="6f88e-117">Comprobar un valor hash</span><span class="sxs-lookup"><span data-stu-id="6f88e-117">Verifying a Hash</span></span>

 <span data-ttu-id="6f88e-118">Los datos pueden compararse con un valor hash para determinar su integridad.</span><span class="sxs-lookup"><span data-stu-id="6f88e-118">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="6f88e-119">Normalmente, el valor hash de los datos se calcula en un momento determinado y se protege de algún modo.</span><span class="sxs-lookup"><span data-stu-id="6f88e-119">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="6f88e-120">Posteriormente, se puede calcular de nuevo el valor hash de los datos y compararse con el valor protegido. </span><span class="sxs-lookup"><span data-stu-id="6f88e-120">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="6f88e-121">Si coinciden los dos valores hash, los datos no se han alterado.</span><span class="sxs-lookup"><span data-stu-id="6f88e-121">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="6f88e-122">En caso contrario, los datos se han dañado.</span><span class="sxs-lookup"><span data-stu-id="6f88e-122">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="6f88e-123">Para que este sistema funcione, el valor hash protegido debe cifrarse o mantenerse fuera del alcance de quienes no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="6f88e-123">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="6f88e-124">En el ejemplo siguiente, se compara el valor hash anterior de una cadena con un valor hash nuevo.</span><span class="sxs-lookup"><span data-stu-id="6f88e-124">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="6f88e-125">En este ejemplo, se recorre cada byte de los valores hash y se realiza una comparación.</span><span class="sxs-lookup"><span data-stu-id="6f88e-125">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="6f88e-126">Si los dos valores hash coinciden, este código mostrará lo siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="6f88e-126">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="6f88e-127">Si no coinciden, el código muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f88e-127">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f88e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f88e-128">See also</span></span>

- [<span data-ttu-id="6f88e-129">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="6f88e-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="6f88e-130">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="6f88e-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="6f88e-131">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="6f88e-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="6f88e-132">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="6f88e-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
