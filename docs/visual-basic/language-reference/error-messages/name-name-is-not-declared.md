---
title: "No se ha declarado el nombre &#39;&lt;nombre&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30451"
  - "vbc30451"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30451"
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# No se ha declarado el nombre &#39;&lt;nombre&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una instrucción hace referencia a un elemento de programación, pero el compilador no puede encontrar un elemento con ese nombre exacto.  
  
 **Identificador de error:** BC30451  
  
### Para corregir este error  
  
1.  Compruebe que el nombre de la instrucción de referencia esté bien escrito.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no distingue mayúsculas de minúsculas, pero cualquier otra variación en la ortografía se considera un nombre completamente diferente.  Observe que el subrayado \(`_`\) forma parte del nombre y, por consiguiente, de la ortografía.  
  
2.  Compruebe que tiene el operador de acceso a miembros \(`.`\) entre un objeto y su miembro.  Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> denominado `TextBox1`, para tener acceso a su propiedad <xref:System.Windows.Forms.TextBoxBase.Text%2A> debe escribir `TextBox1.Text`.  Si en vez de esto escribe `TextBox1Text`, ha creado un nombre diferente.  
  
3.  Si la ortografía es correcta y la sintaxis de cualquier acceso a miembros de objeto es correcta, compruebe que se ha declarado el elemento.  Para obtener más información, vea [Elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Si se ha declarado el elemento de programación, compruebe que está dentro del ámbito.  Si la instrucción de referencia está fuera de la región que declara el elemento de programación, podría necesitar calificar el nombre de elemento.  Para obtener más información, vea [Ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## Vea también  
 [Resumen de constantes y declaraciones](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)