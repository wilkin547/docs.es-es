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
ms.openlocfilehash: b3c9452f8d144fb18ea3efcb35b85caed80e8692
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819351"
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Especifica que Visual Basic debe serializar todas las cadenas como valores Unicode independientemente del nombre del procedimiento externo que se declara.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información debe tener para llamar correctamente al procedimiento. Esta información incluye dónde se encuentra el procedimiento, el cómo se identifica, su secuencia de llamada y el tipo de valor devuelto y el carácter de cadena juego que utiliza. El [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 El `charsetmodifier` parte en la `Declare` instrucción proporciona la información del conjunto de caracteres para serializar cadenas durante una llamada al procedimiento externo. También afecta a cómo Visual Basic busca el archivo externo para el nombre del procedimiento externo. El `Unicode` modificador especifica que Visual Basic debe serializar todas las cadenas como valores Unicode y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.  
  
 Si se especifica ningún modificador de conjunto de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Comentarios  
 El `Unicode` modificador se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas de desarrollador de dispositivos inteligentes  
 No se admite esta palabra clave.  
  
## <a name="see-also"></a>Vea también

- [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
