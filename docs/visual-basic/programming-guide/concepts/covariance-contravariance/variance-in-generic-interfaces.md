---
title: "Varianza en Interfaces genéricas (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a>Varianza en Interfaces genéricas (Visual Basic)
.NET framework 4 introdujo la compatibilidad con la varianza para varias interfaces genéricas existentes. Compatibilidad con la varianza habilita la conversión implícita de las clases que implementan estas interfaces. Las interfaces siguientes son ahora variantes:  
  
-   <xref:System.Collections.Generic.IEnumerable%601>(T es covariante)</xref:System.Collections.Generic.IEnumerable%601>  
  
-   <xref:System.Collections.Generic.IEnumerator%601>(T es covariante)</xref:System.Collections.Generic.IEnumerator%601>  
  
-   <xref:System.Linq.IQueryable%601>(T es covariante)</xref:System.Linq.IQueryable%601>  
  
-   <xref:System.Linq.IGrouping%602>(`TKey` y `TElement` son covariantes)</xref:System.Linq.IGrouping%602>  
  
-   <xref:System.Collections.Generic.IComparer%601>(T es contravariante)</xref:System.Collections.Generic.IComparer%601>  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601>(T es contravariante)</xref:System.Collections.Generic.IEqualityComparer%601>  
  
-   <xref:System.IComparable%601>(T es contravariante)</xref:System.IComparable%601>  
  
 La covarianza permite que un método de tipo de valor devuelto más derivado que el definido por el parámetro de tipo genérico de la interfaz. Para ilustrar la característica de covarianza, considere estas interfaces genéricas: `IEnumerable(Of Object)` y `IEnumerable(Of String)`. El `IEnumerable(Of String)` interfaz no hereda la `IEnumerable(Of Object)` interfaz. Sin embargo, el `String` tipo heredar el `Object` tipo y en algunos casos desee asignar objetos de estas interfaces entre sí. Esto se muestra en el ejemplo de código siguiente.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 En versiones anteriores de .NET Framework, este código produce un error de compilación en Visual Basic con `Option Strict On`. Pero ahora puede usar `strings` en lugar de `objects`, como se muestra en el ejemplo anterior, porque la <xref:System.Collections.Generic.IEnumerable%601>interfaz es covariante.</xref:System.Collections.Generic.IEnumerable%601>  
  
 La contravarianza permite un método tenga tipos de argumento menos derivados que el especificado por el parámetro genérico de la interfaz. Para ilustrar la contravarianza, suponga que ha creado un `BaseComparer` clase para comparar instancias de la `BaseClass` clase. La clase `BaseComparer` implementa la interfaz `IEqualityComparer(Of BaseClass)`. Porque la <xref:System.Collections.Generic.IEqualityComparer%601>interfaz es ahora contravariante, puede usar `BaseComparer` para comparar instancias de las clases que heredan la `BaseClass` clase</xref:System.Collections.Generic.IEqualityComparer%601> Esto se muestra en el ejemplo de código siguiente.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Para obtener más ejemplos, vea [utilizar varianza en Interfaces para las colecciones genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 Para tipos de referencia sólo se admite la varianza en interfaces genéricas. Tipos de valor no admiten la varianza. Por ejemplo, `IEnumerable(Of Integer)` no se puede convertir implícitamente a `IEnumerable(Of Object)`, como enteros se representan mediante un tipo de valor.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 También es importante recordar que las clases que implementan interfaces variantes siguen siendo invariables. Por ejemplo, aunque <xref:System.Collections.Generic.List%601>implementa la interfaz covariante <xref:System.Collections.Generic.IEnumerable%601>, no se puede convertir implícitamente `List(Of Object)` a `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601> Esto se muestra en el ejemplo de código siguiente.  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar la varianza en Interfaces para las colecciones genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Crear Interfaces genéricas variantes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [Interfaces genéricas](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf)   
 [Varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
