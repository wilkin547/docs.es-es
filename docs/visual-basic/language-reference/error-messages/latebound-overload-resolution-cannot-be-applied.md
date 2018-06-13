---
title: No se puede aplicar la resolución de sobrecarga enlazada a &#39; &lt;nombreProcedimiento&gt; &#39; porque la instancia de acceso es un tipo de interfaz
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: e41cbf30f06547ef39553e31542e4e8b6df49a3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589885"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a>No se puede aplicar la resolución de sobrecarga enlazada a &#39; &lt;nombreProcedimiento&gt; &#39; porque la instancia de acceso es un tipo de interfaz
El compilador está intentando resolver una referencia a una propiedad o procedimiento sobrecargados, pero se produce un error en la referencia porque es un argumento de tipo `Object` y el objeto que hace referencia tiene el tipo de datos de una interfaz. El `Object` argumento hace que el compilador para resolver la referencia como en tiempo de ejecución.  
  
 En estas circunstancias, el compilador resuelve la sobrecarga a través de la clase de implementación en lugar de a través de la interfaz subyacente. Si la clase cambia el nombre de una de las versiones sobrecargadas, el compilador no tiene en cuenta que la versión sea una sobrecarga porque su nombre es distinto. Esto hace al compilador que omita la versión cuyo nombre ha cambiado cuando podría haber sido la opción correcta para resolver la referencia.  
  
 **Id. de error:** BC30933  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Use `CType` convertir el argumento de `Object` al tipo especificado por la firma de la sobrecarga que desea llamar.  
  
     Tenga en cuenta que no sirve para convertir el objeto que hace referencia a la interfaz subyacente. Primero debe convertir el argumento para evitar este error.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una llamada a una sobrecarga `Sub` procedimiento que se produzca este error en tiempo de compilación.  
  
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
  
 En el ejemplo anterior, si el compilador permite que la llamada a `s1` tal y como se escribe, la resolución tendrá lugar a través de la clase `c1` en lugar de la interfaz `i1`. Esto significaría que el compilador no consideraría `s2` porque su nombre es distinto en `c1`, aunque es la opción correcta tal como se define por `i1`.  
  
 Puede corregir el error cambiando la llamada a cualquiera de las siguientes líneas de código:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Cada una de las líneas de código anteriores convierte de forma explícita el `Object` variable `o1` a uno de los tipos de parámetro definidos para las sobrecargas.  
  
## <a name="see-also"></a>Vea también  
 [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Resolución de sobrecargas](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)
