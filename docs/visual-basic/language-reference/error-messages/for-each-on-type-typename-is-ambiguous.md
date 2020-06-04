---
title: La instrucción 'For Each' en el tipo '<typename>' es ambigua porque el tipo implementa varias creaciones de instancias de 'System.Collections.Generic.IEnumerable(Of T)'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 153a2640d66f48660f21339aaf0ecc8eaa10f51f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402971"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a>La instrucción 'For Each' en el tipo '\<typename>' es ambigua porque el tipo implementa varias creaciones de instancias de 'System.Collections.Generic.IEnumerable(Of T)'
Una `For Each` instrucción especifica una variable de iterador que tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método.  
  
 La variable de iterador debe ser de un tipo que implementa <xref:System.Collections.IEnumerable?displayProperty=nameWithType> la <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaz o en uno de los `Collections` espacios de nombres de la .NET Framework. Una clase puede implementar más de una interfaz genérica construida con un argumento de tipo diferente para cada construcción. Si una clase que hace esto se usa para la variable de iterador, esa variable tiene más de un <xref:System.Collections.IEnumerable.GetEnumerator%2A> método. En tal caso, Visual Basic no puede elegir el método al que llamar.  
  
 **Identificador de error:** BC32096  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Use el operador [DirectCast](../operators/directcast-operator.md) o [TryCast](../operators/trycast-operator.md) para convertir el tipo de variable de iterador en la interfaz que define el <xref:System.Collections.IEnumerable.GetEnumerator%2A> método que desea usar.  
  
## <a name="see-also"></a>Consulte también

- [Instrucción For Each...Next](../statements/for-each-next-statement.md)
- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
