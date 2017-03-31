---
title: "Varianza en interfaces genéricas (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4c4f3ab00b4de2a6f38858dd5f332db3d47eb85b
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-c"></a>Varianza en interfaces genéricas (C#)
En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes. La compatibilidad con la varianza permite la conversión implícita de clases que implementan estas interfaces. Las interfaces siguientes ahora son variantes:  
  
-   <xref:System.Collections.Generic.IEnumerable%601> (T es covariante)  
  
-   <xref:System.Collections.Generic.IEnumerator%601> (T es covariante)  
  
-   <xref:System.Linq.IQueryable%601> (T es covariante)  
  
-   <xref:System.Linq.IGrouping%602> (`TKey` y `TElement` son covariantes)  
  
-   <xref:System.Collections.Generic.IComparer%601> (T es contravariante)  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601> (T es contravariante)  
  
-   <xref:System.IComparable%601> (T es contravariante)  
  
 La covarianza permite que un método tenga un tipo de valor devuelto más derivado que los que se definen en los parámetros de tipo genérico de la interfaz. Para ilustrar la característica de la covarianza, considere estas interfaces genéricas: `IEnumerable<Object>` y `IEnumerable<String>`. La interfaz `IEnumerable<String>` no hereda la interfaz `IEnumerable<Object>`. En cambio, el tipo `String` hereda el tipo `Object`, y en algunos casos puede que quiera asignar objetos de estas interfaces entre sí. Esto se muestra en el ejemplo de código siguiente.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 En versiones anteriores de .NET Framework, este código provoca un error de compilación en C# con `Option Strict On`. Pero ahora puede usar `strings` en lugar de `objects`, como se muestra en el ejemplo anterior, porque la interfaz <xref:System.Collections.Generic.IEnumerable%601> es covariante.  
  
 La contravarianza permite que un método tenga tipos de argumento menos derivados que los que se especifican en el parámetro genérico de la interfaz. Para ilustrar la contravarianza, se presupone que ha creado una clase `BaseComparer` para comparar instancias de la clase `BaseClass`. La clase `BaseComparer` implementa la interfaz `IEqualityComparer<BaseClass>`. Como la interfaz <xref:System.Collections.Generic.IEqualityComparer%601> ahora es contravariante, puede usar `BaseComparer` para comparar instancias de clases que heredan la clase `BaseClass`. Esto se muestra en el ejemplo de código siguiente.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Para obtener más ejemplos, vea [Usar la varianza en interfaces para las colecciones genéricas (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 La varianza para interfaces genéricas solo es compatible con tipos de referencia. Los tipos de valor no admiten la varianza. Por ejemplo, `IEnumerable<int>` no puede convertirse implícitamente en `IEnumerable<object>`, porque los enteros se representan mediante un tipo de valor.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 También es importante recordar que las clases que implementan las interfaces variantes siguen siendo invariables. Por ejemplo, aunque <xref:System.Collections.Generic.List%601> implemente la interfaz covariante <xref:System.Collections.Generic.IEnumerable%601>, no puede convertir implícitamente `List<Object>` en `List<String>`. Esto se muestra en el siguiente código de ejemplo.  
  
```cs  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar la varianza en interfaces para las colecciones genéricas (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Crear interfaces genéricas variantes (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [Interfaces genéricas](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf)   
 [Varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
