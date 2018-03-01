---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 042908b8427de2de0de96bbb32df7be018bb915c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
