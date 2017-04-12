---
title: Nombre &quot;&lt;nombre&gt;&quot; no se ha declarado | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
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
ms.openlocfilehash: 81b6862a7f8ceb7998b2ea53336ed3af46b1db5f
ms.lasthandoff: 03/13/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a>Nombre '&lt;nombre&gt;' no se ha declarado
La instrucción hace referencia a un elemento de programación, pero el compilador no encuentra un elemento con ese nombre exacto.  
  
 **Id. de error:** BC30451  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe que el nombre de la instrucción de referencia esté bien escrito. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]distingue mayúsculas de minúsculas, pero cualquier otra variación en la ortografía se considera como un nombre completamente distinto. Tenga en cuenta que el carácter de subrayado (`_`) es parte del nombre y, por tanto, parte de la ortografía.  
  
2.  Compruebe que tiene el operador de acceso a miembro (`.`) entre un objeto y su miembro. Por ejemplo, si tiene un <xref:System.Windows.Forms.TextBox>control denominado `TextBox1`para tener acceso a su <xref:System.Windows.Forms.TextBoxBase.Text%2A>propiedad debe escribir `TextBox1.Text`.</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox> Si en su lugar escribe `TextBox1Text`, ha creado un nombre diferente.  
  
3.  Si la ortografía es correcta y la sintaxis de cualquier acceso a miembros de objeto es correcta, compruebe que el elemento se ha declarado. Para obtener más información, consulte [elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Si se ha declarado el elemento de programación, compruebe que esté dentro del ámbito. Si la instrucción de referencia está fuera de la región que declara el elemento de programación, debe calificar el nombre del elemento. Para obtener más información, consulte [ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="see-also"></a>Vea también  
 [Resumen de constantes y declaraciones](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
