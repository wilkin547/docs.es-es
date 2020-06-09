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
# <a name="how-to-use-data-protection"></a>Procedimiento para usar la protección de datos
.NET Framework proporciona acceso a la API de protección de datos (DPAPI), que permite cifrar datos usando la información del equipo o la cuenta del usuario actual.  Cuando se usa la DPAPI, se alivia el difícil problema de generar y almacenar explícitamente una clave criptográfica.  
  
 Use la clase <xref:System.Security.Cryptography.ProtectedMemory> para cifrar una matriz de bytes en memoria.  Esta funcionalidad está disponible en Microsoft Windows XP y en los sistemas operativos posteriores.  Puede especificar que la memoria cifrada por el proceso actual pueda ser descifrada solo por el proceso actual, por todos los procesos o desde el mismo contexto de usuario.  Consulte la enumeración <xref:System.Security.Cryptography.MemoryProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedMemory>.  
  
 Use la clase <xref:System.Security.Cryptography.ProtectedData> para cifrar una copia de una matriz de bytes. Esta funcionalidad está disponible en Microsoft Windows 2000 y en los sistemas operativos posteriores.  Puede especificar que los datos cifrados por la cuenta de usuario actual solo puedan ser descifrados por la misma cuenta de usuario o que puedan ser descifrados por cualquier cuenta del equipo.  Consulte la enumeración <xref:System.Security.Cryptography.DataProtectionScope> para obtener una descripción detallada de las opciones de <xref:System.Security.Cryptography.ProtectedData>.  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a>Para cifrar los datos en memoria mediante la protección de datos  
  
1. Llame al método <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> estático mientras pasa la matriz de bytes que se vaya a cifrar, la entropía y el ámbito de la protección de memoria.  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a>Para descifrar los datos en memoria mediante la protección de datos  
  
1. Llame al método <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> estático mientras pasa la matriz de bytes que se vaya a descifrar y el ámbito de la protección de memoria.  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a>Para cifrar datos en un archivo o una secuencia usando la protección de datos  
  
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
  
- Incluya una referencia a `System.Security.dll`.  
  
- Incluya el espacio de nombres <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> y <xref:System.Text>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
