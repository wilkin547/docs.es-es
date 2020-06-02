---
title: Asegurar la integridad de los datos mediante códigos hash
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 4938cd75af32caa4f9da6ed682f18e9f6c73ad5b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288347"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="8a63c-102">Asegurar la integridad de los datos mediante códigos hash</span><span class="sxs-lookup"><span data-stu-id="8a63c-102">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="8a63c-103">Un valor hash es un valor numérico de longitud fija que solo identifica datos.</span><span class="sxs-lookup"><span data-stu-id="8a63c-103">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="8a63c-104">Los valores hash representan grandes cantidades de datos como valores numéricos mucho menores, por lo que se usan con firmas digitales.</span><span class="sxs-lookup"><span data-stu-id="8a63c-104">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="8a63c-105">Puede firmar un valor hash de forma más eficaz que un valor mayor.</span><span class="sxs-lookup"><span data-stu-id="8a63c-105">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="8a63c-106">Los valores hash también son útiles para comprobar la integridad de datos enviados a través de canales no seguros.</span><span class="sxs-lookup"><span data-stu-id="8a63c-106">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="8a63c-107">El valor hash de los datos recibidos puede compararse con el valor hash de los datos porque se envió para determinar si se alteraron los datos.</span><span class="sxs-lookup"><span data-stu-id="8a63c-107">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
 <span data-ttu-id="8a63c-108">En este tema, se describe cómo generar y comprobar códigos hash mediante las clases en el espacio de nombres <xref:System.Security.Cryptography?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8a63c-108">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="8a63c-109">Generar un valor hash</span><span class="sxs-lookup"><span data-stu-id="8a63c-109">Generating a Hash</span></span>  
 <span data-ttu-id="8a63c-110">Las clases hash administradas pueden aplicar un valor hash a una matriz de bytes o a un objeto de secuencia administrado.</span><span class="sxs-lookup"><span data-stu-id="8a63c-110">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="8a63c-111">En el ejemplo siguiente, se utiliza el algoritmo hash SHA1 para crear un valor hash para una cadena.</span><span class="sxs-lookup"><span data-stu-id="8a63c-111">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="8a63c-112">El ejemplo utiliza la clase <xref:System.Text.UnicodeEncoding> para convertir la cadena en una matriz de bytes que aplica un valor hash mediante el uso de la clase <xref:System.Security.Cryptography.SHA1Managed>.</span><span class="sxs-lookup"><span data-stu-id="8a63c-112">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA1Managed> class.</span></span> <span data-ttu-id="8a63c-113">Posteriormente el valor hash se muestra en la consola.</span><span class="sxs-lookup"><span data-stu-id="8a63c-113">The hash value is then displayed to the console.</span></span>  

 <span data-ttu-id="8a63c-114">Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="8a63c-114">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span></span>
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="8a63c-115">Este código mostrará la cadena siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="8a63c-115">This code will display the following string to the console:</span></span>  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="8a63c-116">Comprobar un valor hash</span><span class="sxs-lookup"><span data-stu-id="8a63c-116">Verifying a Hash</span></span>  
 <span data-ttu-id="8a63c-117">Los datos pueden compararse con un valor hash para determinar su integridad.</span><span class="sxs-lookup"><span data-stu-id="8a63c-117">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="8a63c-118">Normalmente, el valor hash de los datos se calcula en un momento determinado y se protege de algún modo.</span><span class="sxs-lookup"><span data-stu-id="8a63c-118">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="8a63c-119">Posteriormente, se puede calcular de nuevo el valor hash de los datos y compararse con el valor protegido. </span><span class="sxs-lookup"><span data-stu-id="8a63c-119">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="8a63c-120">Si coinciden los dos valores hash, los datos no se han alterado.</span><span class="sxs-lookup"><span data-stu-id="8a63c-120">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="8a63c-121">En caso contrario, los datos se han dañado.</span><span class="sxs-lookup"><span data-stu-id="8a63c-121">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="8a63c-122">Para que este sistema funcione, el valor hash protegido debe cifrarse o mantenerse fuera del alcance de quienes no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="8a63c-122">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="8a63c-123">En el ejemplo siguiente, se compara el valor hash anterior de una cadena con un valor hash nuevo.</span><span class="sxs-lookup"><span data-stu-id="8a63c-123">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="8a63c-124">En este ejemplo, se recorre cada byte de los valores hash y se realiza una comparación.</span><span class="sxs-lookup"><span data-stu-id="8a63c-124">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="8a63c-125">Si los dos valores hash coinciden, este código mostrará lo siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="8a63c-125">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="8a63c-126">Si no coinciden, el código muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a63c-126">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a63c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a63c-127">See also</span></span>

- [<span data-ttu-id="8a63c-128">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="8a63c-128">Cryptographic Services</span></span>](cryptographic-services.md)
