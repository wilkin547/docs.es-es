---
title: Crear un esquema criptográfico
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2db6d4229ac777801aff792c86fe0e5e9a1b4994
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080272"
---
# <a name="creating-a-cryptographic-scheme"></a>Crear un esquema criptográfico
Los componentes criptográficos de .NET Framework se pueden combinar para crear distintos esquemas para cifrar y descifrar datos.  
  
 Un esquema criptográfico simple para cifrar y descifrar datos podría especificar los siguientes pasos:  
  
1.  Cada parte genera un par de claves pública y privada.  
  
2.  Las partes intercambian sus claves públicas.  
  
3.  Cada parte genera una clave secreta para el cifrado TripleDES, por ejemplo, y cifra la clave recién creada con la clave pública de la otra parte.  
  
4.  Una parte envía los datos a la otra y combina la clave secreta de la otra con la suya propia en un determinado orden para crear una nueva clave secreta.  
  
5.  Después, las partes inician una conversación mediante el cifrado simétrico.  
  
 Crear un esquema criptográfico no es una tarea trivial. Para obtener más información sobre el uso de criptografía, vea el tema criptografía en la documentación de Platform SDK en http://msdn.microsoft.com/library.  
  
## <a name="see-also"></a>Vea también

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
