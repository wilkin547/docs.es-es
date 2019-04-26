---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 98dafab3e524ea371bba228eb231e28d46cc3b4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802562"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Especifica que Visual Basic debe serializar todas las cadenas en valores de American National Standards Institute (ANSI) independientemente del nombre del procedimiento externo que se declara.  
  
 Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente. Esta información incluye dónde se encuentra el procedimiento, el cómo se identifica, su secuencia de llamada y el tipo de valor devuelto y el carácter de cadena juego que utiliza. El [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.  
  
 El `charsetmodifier` parte en la `Declare` instrucción proporciona la información del conjunto de caracteres para la serialización de cadenas durante una llamada al procedimiento externo. También afecta a cómo Visual Basic busca el archivo externo para el nombre del procedimiento externo. El `Ansi` modificador especifica que Visual Basic debe serializar todas las cadenas como valores ANSI y buscar el procedimiento sin modificar su nombre durante la búsqueda.  
  
 Si se especifica ningún modificador de conjunto de caracteres, `Ansi` es el valor predeterminado.  
  
## <a name="remarks"></a>Comentarios  
 El `Ansi` modificador se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Notas de desarrollador de dispositivos inteligentes  
 No se admite esta palabra clave.  
  
## <a name="see-also"></a>Vea también

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
