---
title: Crear un esquema criptográfico
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
ms.openlocfilehash: 1478873c1c2dc73ca31c9078e39a3902966bf674
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288425"
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
  
## <a name="see-also"></a>Consulte también

- [Servicios criptográficos](cryptographic-services.md)
