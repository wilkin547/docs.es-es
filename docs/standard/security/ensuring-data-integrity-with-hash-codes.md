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
# <a name="ensuring-data-integrity-with-hash-codes"></a>Asegurar la integridad de los datos mediante códigos hash

Un valor hash es un valor numérico de longitud fija que solo identifica datos. Los valores hash representan grandes cantidades de datos como valores numéricos mucho menores, por lo que se usan con firmas digitales. Puede firmar un valor hash de forma más eficaz que un valor mayor. Los valores hash también son útiles para comprobar la integridad de datos enviados a través de canales no seguros. El valor hash de los datos recibidos puede compararse con el valor hash de los datos porque se envió para determinar si se alteraron los datos.  
  
En este tema, se describe cómo generar y comprobar códigos hash mediante las clases en el espacio de nombres <xref:System.Security.Cryptography>.  
  
## <a name="generating-a-hash"></a>Generar un valor hash

 Las clases hash administradas pueden aplicar un valor hash a una matriz de bytes o a un objeto de secuencia administrado. En el ejemplo siguiente, se utiliza el algoritmo hash SHA1 para crear un valor hash para una cadena. El ejemplo utiliza la clase <xref:System.Text.UnicodeEncoding> para convertir la cadena en una matriz de bytes que aplica un valor hash mediante el uso de la clase <xref:System.Security.Cryptography.SHA256>. Posteriormente el valor hash se muestra en la consola.  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 Este código mostrará la cadena siguiente en la consola:  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a>Comprobar un valor hash

 Los datos pueden compararse con un valor hash para determinar su integridad. Normalmente, el valor hash de los datos se calcula en un momento determinado y se protege de algún modo. Posteriormente, se puede calcular de nuevo el valor hash de los datos y compararse con el valor protegido.  Si coinciden los dos valores hash, los datos no se han alterado. En caso contrario, los datos se han dañado. Para que este sistema funcione, el valor hash protegido debe cifrarse o mantenerse fuera del alcance de quienes no sean de confianza.  
  
 En el ejemplo siguiente, se compara el valor hash anterior de una cadena con un valor hash nuevo. En este ejemplo, se recorre cada byte de los valores hash y se realiza una comparación.  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 Si los dos valores hash coinciden, este código mostrará lo siguiente en la consola:  
  
```console  
The hash codes match.  
```  
  
 Si no coinciden, el código muestra lo siguiente:  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a>Consulte también

- [Modelo de criptografía](cryptography-model.md)
- [servicios criptográficos](cryptographic-services.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
