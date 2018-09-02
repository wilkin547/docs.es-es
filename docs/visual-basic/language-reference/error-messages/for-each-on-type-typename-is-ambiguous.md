---
title: '&#39;Para cada&#39; en tipo &#39; &lt;typename&gt; &#39; es ambigua porque el tipo implementa varias creaciones de instancias de &#39;System.Collections.Generic.IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 8c48a7134eb8da83fb418b9aa91d55dcbe8e8bcb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456310"
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39;Para cada&#39; en tipo &#39; &lt;typename&gt; &#39; es ambigua porque el tipo implementa varias creaciones de instancias de &#39;System.Collections.Generic.IEnumerable (Of T)&#39;
Un `For Each` instrucción especifica una variable de iterador que tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.  
  
 La variable de iterador debe ser de un tipo que implementa el <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaz en uno de los `Collections` espacios de nombres de los [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Es posible que una clase implementar más de una interfaz genérica construida, con un argumento de tipo diferente para cada construcción. Si se usa una clase que hace esto para la variable de iterador, esa variable tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método. En tal caso, Visual Basic no puede elegir qué método va a llamar.  
  
 **Identificador de error:** BC32096  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Usar [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md) convertir el tipo de variable de iterador para la interfaz que define el <xref:System.Collections.IEnumerable.GetEnumerator%2A> método que desee usar.  
  
## <a name="see-also"></a>Vea también  
 [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
