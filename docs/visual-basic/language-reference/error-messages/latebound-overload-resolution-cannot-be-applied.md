---
title: "La resoluci&#243;n de sobrecarga enlazada tard&#237;amente no se puede aplicar a &#39;&lt;nombre de procedimiento&gt;&#39; porque la instancia de acceso es un tipo de interfaz | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30933"
  - "bc30933"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30933"
  - "resolución de sobrecargas, con argumento enlazado tardíamente"
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# La resoluci&#243;n de sobrecarga enlazada tard&#237;amente no se puede aplicar a &#39;&lt;nombre de procedimiento&gt;&#39; porque la instancia de acceso es un tipo de interfaz
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El compilador está intentando resolver una referencia a una propiedad o procedimiento sobrecargados, pero la referencia no funciona porque uno de los argumentos es del tipo `Object` y el objeto que hace referencia a él tiene el tipo de datos de una interfaz.  El argumento `Object` obliga al compilador a resolver la referencia como enlazada en tiempo de ejecución.  
  
 En estas circunstancias, el compilador resuelve la sobrecarga mediante la clase que la implementa en lugar de a través de la interfaz subyacente.  Si la clase cambia el nombre de una de las versiones sobrecargadas, el compilador no considera que esa versión sea una sobrecarga porque su nombre es distinto.  A su vez, esto hace que el compilador omita la versión cuyo nombre se ha cambiado cuando podría haber sido la opción correcta para resolver la referencia.  
  
 **Identificador de error:** BC30933  
  
### Para corregir este error  
  
-   Utilice `CType` para convertir el argumento de `Object` al tipo especificado por la firma de la sobrecarga a la que desea llamar.  
  
     Observe que no sirve de nada convertir el objeto que hace referencia a la interfaz subyacente.  Debe convertir el argumento para evitar este error.  
  
## Ejemplo  
 El ejemplo siguiente muestra una llamada a un procedimiento `Sub` sobrecargado que produce este error en tiempo de compilación.  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 En el ejemplo anterior, si el compilador permitiera la llamada a `s1` tal y como está escrita, la resolución se produciría mediante la clase `c1` en lugar de a través de la interfaz `i1`.  Esto significaría que el compilador no tendría en cuenta `s2` porque su nombre es distinto en `c1`, aun cuando es la opción correcta definida por `i1`.  
  
 Puede corregir el error cambiando la llamada a cualquiera de las líneas de código siguientes:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Cada una de las líneas de código anteriores convierte explícitamente la variable `o1` de variable `Object` a uno de los tipos de parámetro definidos para las sobrecargas.  
  
## Vea también  
 [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Resolución de sobrecargas](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md)