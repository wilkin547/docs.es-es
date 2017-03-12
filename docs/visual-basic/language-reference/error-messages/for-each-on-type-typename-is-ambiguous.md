---
title: "La instrucci&#243;n &#39;For Each&#39; en el tipo &#39;&lt;nombre de tipo&gt;&#39; es ambigua porque el tipo implementa varias creaciones de instancias de &#39;System.Collections.Generic.IEnumerable(Of T)&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32096"
  - "bc32096"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32096"
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# La instrucci&#243;n &#39;For Each&#39; en el tipo &#39;&lt;nombre de tipo&gt;&#39; es ambigua porque el tipo implementa varias creaciones de instancias de &#39;System.Collections.Generic.IEnumerable(Of T)&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una instrucción `For Each` especifica una variable de iterador que tiene más de un método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.  
  
 La variable de iterador debe ser de un tipo que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=fullName> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> en uno de los espacios de nombres `Collections` de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Es posible que una clase implemente más de una interfaz genérica construida, que utiliza un argumento de tipo diferente para cada construcción.  Si se utiliza una clase que hace esto para la variable de iterador, esa variable tiene más de un método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.  En este caso, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no se puede elegir a qué método llamar.  
  
 **Identificador de error:** BC32096  
  
### Para corregir este error  
  
-   Utilice [DirectCast \(Operador\)](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast \(Operador\)](../../../visual-basic/language-reference/operators/trycast-operator.md) para convertir el tipo variable del iterador a la interfaz que define el método <xref:System.Collections.IEnumerable.GetEnumerator%2A> que desee utilizar.  
  
## Vea también  
 [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)