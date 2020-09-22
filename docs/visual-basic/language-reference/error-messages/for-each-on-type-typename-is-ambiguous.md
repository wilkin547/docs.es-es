---
title: La instrucción 'For Each' en el tipo '<typename>' es ambigua porque el tipo implementa varias creaciones de instancias de 'System.Collections.Generic.IEnumerable(Of T)'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: d04a77291ecf09f88ad189667540e9e353246f28
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874084"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="f06a6-102">La instrucción 'For Each' en el tipo '\<typename>' es ambigua porque el tipo implementa varias creaciones de instancias de 'System.Collections.Generic.IEnumerable(Of T)'</span><span class="sxs-lookup"><span data-stu-id="f06a6-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>

<span data-ttu-id="f06a6-103">Una `For Each` instrucción especifica una variable de iterador que tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f06a6-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="f06a6-104">La variable de iterador debe ser de un tipo que implementa <xref:System.Collections.IEnumerable?displayProperty=nameWithType> la <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaz o en uno de los `Collections` espacios de nombres de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f06a6-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the .NET Framework.</span></span> <span data-ttu-id="f06a6-105">Una clase puede implementar más de una interfaz genérica construida con un argumento de tipo diferente para cada construcción.</span><span class="sxs-lookup"><span data-stu-id="f06a6-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="f06a6-106">Si una clase que hace esto se usa para la variable de iterador, esa variable tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f06a6-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="f06a6-107">En tal caso, Visual Basic no puede elegir el método al que llamar.</span><span class="sxs-lookup"><span data-stu-id="f06a6-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="f06a6-108">**Identificador de error:** BC32096</span><span class="sxs-lookup"><span data-stu-id="f06a6-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f06a6-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f06a6-109">To correct this error</span></span>  
  
- <span data-ttu-id="f06a6-110">Use el operador [DirectCast](../operators/directcast-operator.md) o [TryCast](../operators/trycast-operator.md) para convertir el tipo de variable de iterador en la interfaz que define el <xref:System.Collections.IEnumerable.GetEnumerator%2A> método que desea usar.</span><span class="sxs-lookup"><span data-stu-id="f06a6-110">Use [DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06a6-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f06a6-111">See also</span></span>

- [<span data-ttu-id="f06a6-112">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="f06a6-112">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="f06a6-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="f06a6-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
