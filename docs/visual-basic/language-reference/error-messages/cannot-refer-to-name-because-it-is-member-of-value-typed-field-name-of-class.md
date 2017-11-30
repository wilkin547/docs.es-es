---
title: No se puede hacer referencia a &#39; &lt;nombre&gt;&#39; porque es un miembro del campo de tipo de valor &#39;&lt; nombre&gt;&#39; de la clase &#39;&lt; ClassName&gt;&#39; que tiene &#39; System.MarshalByRefObject &#39; como una clase base
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords: BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>No se puede hacer referencia a &#39; &lt;nombre&gt;&#39; porque es un miembro del campo de tipo de valor &#39;&lt; nombre&gt;&#39; de la clase &#39;&lt; ClassName&gt;&#39; que tiene &#39; System.MarshalByRefObject &#39; como una clase base
La `System.MarshalByRefObject` clase permite a las aplicaciones que admiten el acceso remoto a los objetos en los límites del dominio de aplicación. Los tipos deben heredar de la `MarshalByRejectObject` clase cuando el tipo se utiliza en los límites del dominio de aplicación. No se debe copiar el estado del objeto porque los miembros del objeto no se puede usar fuera del dominio de aplicación en el que se crearon.  
  
 **Id. de error:** BC30310  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe la referencia para asegurarse de que el miembro que se hace referencia es válido.  
  
2.  Califique explícitamente el miembro con el `Me` palabra clave.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.MarshalByRefObject>  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
