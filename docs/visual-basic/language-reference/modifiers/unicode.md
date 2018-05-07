---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: a61fd8e10c39569d92dd84180f678a1ff05a9310
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Especifica que Visual Basic debe calcular las referencias de todas las cadenas con valores de Unicode sin tener en cuenta el nombre del procedimiento externo que se declara.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información necesaria para llamar correctamente al procedimiento. Esta información incluye donde se encuentra el procedimiento, el lo identifica, su secuencia de llamada y el tipo de valor devuelto y juego de caracteres de la cadena que utiliza. El [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 El `charsetmodifier` parte de la `Declare` instrucción proporciona la información del conjunto de caracteres para serializar cadenas durante una llamada al procedimiento externo. También afecta al modo en que Visual Basic busca el archivo externo para el nombre del procedimiento externo. El `Unicode` modificador especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores Unicode y buscar el procedimiento sin modificar su nombre durante la búsqueda.  
  
 Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Comentarios  
 El `Unicode` modificador se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas de desarrollador de Smart Device  
 No se admite esta palabra clave.  
  
## <a name="see-also"></a>Vea también  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
