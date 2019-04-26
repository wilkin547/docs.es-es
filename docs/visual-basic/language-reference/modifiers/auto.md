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
ms.openlocfilehash: e4beb320b3aa0cadb790dd3ab92255496bc32f05
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802711"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework basadas en el nombre externo del procedimiento externo que se declara.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información que debe tener para llamar correctamente al procedimiento. Esta información incluye dónde se encuentra el procedimiento, el cómo se identifica, su secuencia de llamada y el tipo de valor devuelto y el carácter de cadena juego que utiliza. El [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 El `charsetmodifier` parte en la `Declare` instrucción proporciona la información del conjunto de caracteres para la serialización de cadenas durante una llamada al procedimiento externo. También afecta a cómo Visual Basic busca el archivo externo para el nombre del procedimiento externo. El `Auto` modificador especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework y que debe determinar el juego de la plataforma de tiempo de ejecución y, posiblemente, de caracteres base modificar el nombre del procedimiento externo si inicial de búsqueda se produce un error. Para obtener más información, vea "Juegos de caracteres" en [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Si se especifica ningún modificador de conjunto de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Comentarios  
 El `Auto` modificador se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas de desarrollador de dispositivos inteligentes  
 No se admite esta palabra clave.  
  
## <a name="see-also"></a>Vea también

- [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
