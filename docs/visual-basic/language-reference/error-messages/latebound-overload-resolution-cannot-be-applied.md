---
title: La resolución de sobrecarga enlazada tardíamente no se puede aplicar a '<procedurename>' porque la instancia de acceso es un tipo de interfaz
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 1fe3c4a29b542302b3615459142a3c565aa8244f
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513023"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a>La resolución de sobrecarga enlazada tardíamente\<no se puede aplicar a ' nombreprocedimiento > ' porque la instancia de acceso es un tipo de interfaz

El compilador está intentando resolver una referencia a una propiedad o procedimiento sobrecargado, pero se produce un error en la referencia porque `Object` un argumento es de tipo y el objeto de referencia tiene el tipo de datos de una interfaz. El `Object` argumento obliga al compilador a resolver la referencia como enlazada en tiempo de ejecución.

En estas circunstancias, el compilador resuelve la sobrecarga a través de la clase de implementación en lugar de a través de la interfaz subyacente. Si la clase cambia el nombre de una de las versiones sobrecargadas, el compilador no considera que la versión es una sobrecarga porque su nombre es diferente. Esto, a su vez, hace que el compilador omita la versión a la que se ha cambiado el nombre cuando podría haber sido la opción correcta para resolver la referencia.

**IDENTIFICADOR de error:** BC30933

## <a name="to-correct-this-error"></a>Para corregir este error

- Use `CType` para convertir el argumento de `Object` en el tipo especificado por la firma de la sobrecarga a la que desea llamar.

  Tenga en cuenta que no ayuda a convertir el objeto que hace referencia en la interfaz subyacente. Debe convertir el argumento para evitar este error.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra una llamada a un `Sub` procedimiento sobrecargado que produce este error en tiempo de compilación.

```vb
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

En el ejemplo anterior, si el compilador permitía `s1` la llamada a como escrita, la resolución se realizaría `c1` a través de la clase `i1`en lugar de la interfaz. Esto significa que el compilador no tendría `s2` en cuenta porque su nombre es `c1`diferente en, aunque es la opción `i1`correcta tal y como se define en.

Puede corregir el error cambiando la llamada a cualquiera de las siguientes líneas de código:

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

Cada una de las líneas de código anteriores convierte explícitamente `Object` la `o1` variable a uno de los tipos de parámetros definidos para las sobrecargas.

## <a name="see-also"></a>Vea también

- [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Resolución de sobrecargas](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)
