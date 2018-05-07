---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 414998b4bef526060e7ba4f584fa071fbd0acaa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Especifica que Visual Basic debe calcular las referencias de cadenas según las reglas de .NET Framework basadas en el nombre externo del procedimiento externo que se declara.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información necesaria que llamar correctamente al procedimiento. Esta información incluye donde se encuentra el procedimiento, el lo identifica, su secuencia de llamada y el tipo de valor devuelto y juego de caracteres de la cadena que utiliza. El [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 El `charsetmodifier` parte de la `Declare` instrucción proporciona la información del conjunto de caracteres para calcular referencias de cadenas durante una llamada al procedimiento externo. También afecta al modo en que Visual Basic busca el archivo externo para el nombre del procedimiento externo. El `Auto` modificador especifica que Visual Basic debe calcular las referencias de cadenas según las reglas de .NET Framework y que debe determinar el juego de la plataforma de tiempo de ejecución y, posiblemente, de caracteres base modificar el nombre del procedimiento externo si la inicial de búsqueda se produce un error. Para obtener más información, vea "Juegos de caracteres" en [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Comentarios  
 El `Auto` modificador se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas de desarrollador de Smart Device  
 No se admite esta palabra clave.  
  
## <a name="see-also"></a>Vea también  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
