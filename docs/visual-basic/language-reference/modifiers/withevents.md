---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 240058a534456ae20c9c129a068bae575ac45eda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Especifica que una o más variables de miembro declaradas hacen referencia a una instancia de una clase que puede provocar eventos.  
  
## <a name="remarks"></a>Comentarios  
 Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante la `Handles` palabra clave.  
  
 Puede usar `WithEvents` sólo en el nivel de clase o módulo. Esto significa que el contexto de la declaración de un `WithEvents` variable debe ser una clase o módulo y no puede ser un archivo de código fuente, el espacio de nombres, la estructura o el procedimiento.  
  
 No se puede utilizar `WithEvents` en un miembro de estructura.  
  
 Puede declarar variables individuales solo, no las matrices, con `WithEvents`.  
  
## <a name="rules"></a>Reglas  
  
-   **Tipos de elemento.** Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase. Sin embargo, no se puede declarar como `Object`. Se debe declarar como la clase específica que puede provocar los eventos.  
  
 El `WithEvents` modificador se puede usar en este contexto: [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
