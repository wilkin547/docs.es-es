---
title: Nombre de &#39; &lt;nombre&gt;&#39; no se ha declarado
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a63ae74c7179d71756e2b9b4bf6b41a71ce12a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="name-39ltnamegt39-is-not-declared"></a>Nombre de &#39; &lt;nombre&gt;&#39; no se ha declarado
Una instrucción hace referencia a un elemento de programación, pero el compilador no encuentra un elemento con ese nombre exacto.  
  
 **Id. de error:** BC30451  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe que el nombre de la instrucción de referencia esté bien escrito. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]distingue mayúsculas de minúsculas, pero cualquier otra variación en la ortografía se considera como un nombre completamente distinto. Tenga en cuenta que el carácter de subrayado (`_`) es parte del nombre y, por tanto, parte de la ortografía.  
  
2.  Compruebe que tiene el operador de acceso de miembro (`.`) entre un objeto y su miembro. Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> denominado `TextBox1`, para tener acceso a su propiedad <xref:System.Windows.Forms.TextBoxBase.Text%2A> debe escribir `TextBox1.Text`. Si en su lugar escribe `TextBox1Text`, ha creado un nombre diferente.  
  
3.  Si la ortografía es correcta y la sintaxis de cualquier acceso a miembros de objeto es correcta, compruebe que se ha declarado el elemento. Para obtener más información, consulte [elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Si se ha declarado el elemento de programación, compruebe que esté dentro del ámbito. Si la instrucción de referencia está fuera de la región que declara el elemento de programación, debe calificar el nombre del elemento. Para obtener más información, consulte [ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="see-also"></a>Vea también  
 [Resumen de constantes y declaraciones](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
