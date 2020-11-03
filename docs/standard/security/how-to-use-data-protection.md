---
title: Procedimiento para usar la protección de datos
description: Aprenda a usar la protección de datos mediante el acceso a la API de protección de datos (DPAPI) en .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
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
ms.openlocfilehash: d3fe7ef3ddbc6e75a248101829b11a8abcb3c15a
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282048"
---
# <a name="how-to-use-data-protection"></a>Procedimiento para usar la protección de datos

> [!NOTE]
> Este artículo se aplica a Windows.
>
> Para obtener información sobre ASP.NET Core, consulte [ASP.net Core protección de datos](/aspnet/core/security/data-protection/introduction).

.NET proporciona acceso a la API de protección de datos (DPAPI), que permite cifrar los datos con la información de la cuenta de usuario o el equipo actual.  Cuando se usa la DPAPI, se alivia el difícil problema de generar y almacenar explícitamente una clave criptográfica.  
  
Use la clase <xref:System.Security.Cryptography.ProtectedData> para cifrar una copia de una matriz de bytes. Esta funcionalidad está disponible en .NET Framework, .NET Core y .NET 5.  Puede especificar que los datos cifrados por la cuenta de usuario actual solo puedan ser descifrados por la misma cuenta de usuario o que puedan ser descifrados por cualquier cuenta del equipo.  Consulte la enumeración <xref:System.Security.Cryptography.DataProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedData>.  
  
## <a name="encrypt-data-to-a-file-or-stream-using-data-protection"></a>Cifrado de datos en un archivo o una secuencia mediante la protección de datos  
  
1. Cree una entropía aleatoria.  
  
2. Llame al método <xref:System.Security.Cryptography.ProtectedData.Protect%2A> estático mientras pasa la matriz de bytes que se vaya a cifrar, la entropía y el ámbito de la protección de datos.  
  
3. Escriba los datos cifrados en un archivo o en una secuencia.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>Para descifrar los datos de un archivo o secuencia usando la protección de datos  
  
1. Lea los datos cifrados desde un archivo o una secuencia.  
  
2. Llame al método <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> estático mientras pasa la matriz de bytes que se vaya a descifrar y el ámbito de la protección de datos.  
  
## <a name="example"></a>Ejemplo

En el siguiente ejemplo de código se muestran dos formas de cifrado y descifrado.  En primer lugar, el ejemplo de código cifra y luego descifra la matriz de bytes en memoria.  A continuación, el ejemplo de código cifra una copia de una matriz de bytes, la guarda en un archivo, vuelve a cargar los datos del archivo y, a continuación, descifra los datos.  El ejemplo muestra los datos originales, los datos cifrados y los datos descifrados.

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  

Este ejemplo se compila y se ejecuta solo cuando el destino es .NET Framework y se ejecuta en Windows.

- Incluya una referencia a `System.Security.dll`.  
  
- Incluya el espacio de nombres <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> y <xref:System.Text>.  
  
## <a name="see-also"></a>Consulte también

- [Modelo de criptografía](cryptography-model.md)
- [servicios criptográficos](cryptographic-services.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
