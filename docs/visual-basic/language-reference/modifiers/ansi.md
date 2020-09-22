---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 8dfd830e4c7ed97c8813da4ad310ee59b26f44f8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90868803"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)

Especifica que Visual Basic debe serializar todas las cadenas en valores de American National Standards Institute (ANSI), independientemente del nombre del procedimiento externo que se está declarando.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente. Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa. La [instrucción Declare](../statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 La `charsetmodifier` parte de la `Declare` instrucción proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo. También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo. El `Ansi` modificador especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores ANSI y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.  
  
 Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Comentarios  

 El `Ansi` modificador se puede usar en este contexto:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas para desarrolladores de Smart Device  

 Esta palabra clave no es compatible.  
  
## <a name="see-also"></a>Consulte también

- [Auto](auto.md)
- [Unicode](unicode.md)
- [Palabras clave](../keywords/index.md)
