---
title: Crear un esquema criptográfico
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
ms.openlocfilehash: 00fff5f346633a9682d75cf6a3be7e8e7d5db7e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706297"
---
# <a name="creating-a-cryptographic-scheme"></a>Crear un esquema criptográfico
Los componentes criptográficos de .NET Framework se pueden combinar para crear distintos esquemas para cifrar y descifrar datos.  
  
 Un esquema criptográfico simple para cifrar y descifrar datos podría especificar los siguientes pasos:  
  
1. Cada parte genera un par de claves pública y privada.  
  
2. Las partes intercambian sus claves públicas.  
  
3. Cada parte genera una clave secreta para el cifrado TripleDES, por ejemplo, y cifra la clave recién creada con la clave pública de la otra parte.  
  
4. Una parte envía los datos a la otra y combina la clave secreta de la otra con la suya propia en un determinado orden para crear una nueva clave secreta.  
  
5. Después, las partes inician una conversación mediante el cifrado simétrico.  
  
 Crear un esquema criptográfico no es una tarea trivial.
  
## <a name="see-also"></a>Vea también

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
