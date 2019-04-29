---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 75d118ee2bd4918c3a936cb341864ddc5315726b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778643"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Especifica que una o más variables de miembro declaradas hacen referencia a una instancia de una clase que puede provocar eventos.  
  
## <a name="remarks"></a>Comentarios  
 Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante el `Handles` palabra clave.  
  
 Puede usar `WithEvents` sólo en el nivel de clase o módulo. Esto significa que el contexto de declaración de un `WithEvents` variable debe ser una clase o módulo y no puede ser un archivo de código fuente, el espacio de nombres, la estructura o el procedimiento.  
  
 No puede usar `WithEvents` en un miembro de estructura.  
  
 Puede declarar solo las variables individuales, no las matrices, con `WithEvents`.  
  
## <a name="rules"></a>Reglas  
  
- **Tipos de elemento.** Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase. Sin embargo, no se puede declarar como `Object`. Se debe declarar como la clase específica que puede provocar los eventos.  
  
 El `WithEvents` modificador se puede usar en este contexto: [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
