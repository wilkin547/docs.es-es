---
title: Palabras clave como nombres de elementos en código (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 2e3613bd4a74da51cf7dbb63e52eddca811ca8e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947661"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Palabras clave como nombres de elementos en código (Visual Basic)
Cualquier elemento de programa, como una variable, una clase o un miembro, puede tener el mismo nombre que una palabra clave restringida. Por ejemplo, puede crear una variable denominada `Loop`. Sin embargo, para hacer referencia a su versión del mismo, que tiene el mismo nombre que `Loop` la palabra clave Restricted, debe precederlo con una cadena de calificación completa o encerrarlo entre corchetes (`[ ]`), como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Si no hace ninguno de estos, Visual Basic supone el uso de la palabra clave Intrinsic `Loop` y genera un error, como en el ejemplo siguiente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Puede usar corchetes al hacer referencia a formularios y controles, y al declarar una variable o definir un procedimiento con el mismo nombre que una palabra clave restringida. Puede ser fácil olvidarse de calificar nombres o incluir corchetes y, por tanto, introducir errores en el código y dificultar su lectura. Por esta razón, se recomienda no usar palabras clave restringidas como nombres de elementos de programa. Sin embargo, si una versión futura de Visual Basic define una nueva palabra clave que entra en conflicto con un nombre de formulario o control existente, puede usar esta técnica al actualizar el código para que funcione con la nueva versión.  
  
> [!NOTE]
> El programa también podría incluir nombres de elementos proporcionados por otros ensamblados a los que se hace referencia. Si estos nombres entran en conflicto con palabras clave restringidas, la colocación de los corchetes hace que Visual Basic los interprete como elementos definidos.  
  
## <a name="see-also"></a>Vea también

- [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
