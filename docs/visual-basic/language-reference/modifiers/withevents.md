---
title: WithEvents (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 708cf6fec78faf2c7a5959a3a2694d237d728882
ms.lasthandoff: 03/13/2017

---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Especifica que una o más variables de miembro declaradas hacen referencia a una instancia de una clase que puede provocar eventos.  
  
## <a name="remarks"></a>Comentarios  
 Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante la `Handles` (palabra clave).  
  
 Puede usar `WithEvents` sólo en el nivel de clase o módulo. Esto significa que el contexto de la declaración de un `WithEvents` variable debe ser una clase o módulo y no puede ser un archivo de código fuente, el espacio de nombres, la estructura o el procedimiento.  
  
 No se puede utilizar `WithEvents` en un miembro de estructura.  
  
 Puede declarar variables individuales sólo: no matrices: con `WithEvents`.  
  
## <a name="rules"></a>Reglas  
  
-   **Tipos de elemento.** Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase. Sin embargo, no se puede declarar como `Object`. Debe declararlas como la clase específica que puede provocar los eventos.  
  
 El `WithEvents` modificador se puede utilizar en este contexto: [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Identificadores](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
