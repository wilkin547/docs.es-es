---
title: '&quot;For Each&quot; en el tipo &quot;&lt;typename&gt;&quot; es ambigua porque el tipo implementa varias creaciones de instancias de &quot;IEnumerable (Of T)&quot; | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
dev_langs:
- VB
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
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
ms.openlocfilehash: 6177b48cdc3bc4085cecb6d73c164684ef1c0bc6
ms.lasthandoff: 03/13/2017

---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>'For Each' en el tipo '&lt;typename&gt;' es ambigua porque el tipo implementa varias creaciones de instancias de 'IEnumerable (Of T)'
Un `For Each` instrucción especifica una variable de iterador que tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A>método.</xref:System.Collections.IEnumerable.GetEnumerator%2A>  
  
 La variable de iterador debe ser de un tipo que implementa el <xref:System.Collections.IEnumerable?displayProperty=fullName>o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>interfaz en uno de los `Collections` espacios de nombres de la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> </xref:System.Collections.IEnumerable?displayProperty=fullName> Es posible que una clase para implementar más de una interfaz genérica construida, con un argumento de tipo diferente para cada construcción. Si se utiliza una clase que hace esto para la variable de iterador, esa variable tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A>método.</xref:System.Collections.IEnumerable.GetEnumerator%2A> En tal caso, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no puede elegir qué método llamar.  
  
 **Id. de error:** BC32096  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Utilice [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md) convertir el tipo de variable de iterador a la interfaz que define el <xref:System.Collections.IEnumerable.GetEnumerator%2A>método que desea utilizar.</xref:System.Collections.IEnumerable.GetEnumerator%2A>  
  
## <a name="see-also"></a>Vea también  
 [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
