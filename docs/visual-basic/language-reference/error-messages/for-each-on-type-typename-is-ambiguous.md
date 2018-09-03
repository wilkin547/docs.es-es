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
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="40bff-102">&#39;Para cada&#39; en tipo &#39; &lt;typename&gt; &#39; es ambigua porque el tipo implementa varias creaciones de instancias de &#39;System.Collections.Generic.IEnumerable (Of T)&#39;</span><span class="sxs-lookup"><span data-stu-id="40bff-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="40bff-103">Un `For Each` instrucción especifica una variable de iterador que tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.</span><span class="sxs-lookup"><span data-stu-id="40bff-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="40bff-104">La variable de iterador debe ser de un tipo que implementa el <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaz en uno de los `Collections` espacios de nombres de los [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40bff-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="40bff-105">Es posible que una clase implementar más de una interfaz genérica construida, con un argumento de tipo diferente para cada construcción.</span><span class="sxs-lookup"><span data-stu-id="40bff-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="40bff-106">Si se usa una clase que hace esto para la variable de iterador, esa variable tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.</span><span class="sxs-lookup"><span data-stu-id="40bff-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="40bff-107">En tal caso, Visual Basic no puede elegir qué método va a llamar.</span><span class="sxs-lookup"><span data-stu-id="40bff-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="40bff-108">**Identificador de error:** BC32096</span><span class="sxs-lookup"><span data-stu-id="40bff-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="40bff-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="40bff-109">To correct this error</span></span>  
  
-   <span data-ttu-id="40bff-110">Usar [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md) convertir el tipo de variable de iterador para la interfaz que define el <xref:System.Collections.IEnumerable.GetEnumerator%2A> método que desee usar.</span><span class="sxs-lookup"><span data-stu-id="40bff-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bff-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="40bff-111">See Also</span></span>  
 [<span data-ttu-id="40bff-112">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="40bff-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="40bff-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="40bff-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
