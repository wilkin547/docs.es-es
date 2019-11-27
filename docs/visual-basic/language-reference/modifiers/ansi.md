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
ms.openlocfilehash: 0c38c2b81af7b4cb8fd1723853a09c5413f805af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344742"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Especifica que Visual Basic debe serializar todas las cadenas en valores de American National Standards Institute (ANSI), independientemente del nombre del procedimiento externo que se está declarando.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente. Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa. La [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 La parte `charsetmodifier` de la instrucción `Declare` proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo. También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo. El modificador `Ansi` especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores ANSI y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.  
  
 Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Comentarios  
 El modificador `Ansi` se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas para desarrolladores de Smart Device  
 Esta palabra clave no es compatible.  
  
## <a name="see-also"></a>Vea también

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
