---
description: "Más información acerca de: BC30933: la resolución de sobrecarga enlazada no se puede aplicar a ' <procedurename> ' porque la instancia de acceso es un tipo de interfaz"
title: La resolución de sobrecarga enlazada tardíamente no se puede aplicar a '<procedurename>' porque la instancia de acceso es un tipo de interfaz
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 3002232c953fa21a10de944bc61e2f0c448ae4fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795916"
---
# <a name="bc30933-latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="cfa0c-103">BC30933: la resolución de sobrecarga enlazada tardíamente no se puede aplicar a ' \<procedurename> ' porque la instancia de acceso es un tipo de interfaz</span><span class="sxs-lookup"><span data-stu-id="cfa0c-103">BC30933: Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>

<span data-ttu-id="cfa0c-104">El compilador está intentando resolver una referencia a una propiedad o procedimiento sobrecargado, pero se produce un error en la referencia porque un argumento es de tipo `Object` y el objeto de referencia tiene el tipo de datos de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-104">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="cfa0c-105">El `Object` argumento obliga al compilador a resolver la referencia como enlazada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-105">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>

<span data-ttu-id="cfa0c-106">En estas circunstancias, el compilador resuelve la sobrecarga a través de la clase de implementación en lugar de a través de la interfaz subyacente.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-106">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="cfa0c-107">Si la clase cambia el nombre de una de las versiones sobrecargadas, el compilador no considera que la versión es una sobrecarga porque su nombre es diferente.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-107">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="cfa0c-108">Esto, a su vez, hace que el compilador omita la versión a la que se ha cambiado el nombre cuando podría haber sido la opción correcta para resolver la referencia.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-108">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>

<span data-ttu-id="cfa0c-109">**Identificador de error:** BC30933</span><span class="sxs-lookup"><span data-stu-id="cfa0c-109">**Error ID:** BC30933</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="cfa0c-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cfa0c-110">To correct this error</span></span>

- <span data-ttu-id="cfa0c-111">Use `CType` para convertir el argumento de `Object` en el tipo especificado por la firma de la sobrecarga a la que desea llamar.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-111">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>

  <span data-ttu-id="cfa0c-112">Tenga en cuenta que no ayuda a convertir el objeto que hace referencia en la interfaz subyacente.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-112">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="cfa0c-113">Debe convertir el argumento para evitar este error.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-113">You must cast the argument to avoid this error.</span></span>

## <a name="example"></a><span data-ttu-id="cfa0c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cfa0c-114">Example</span></span>

<span data-ttu-id="cfa0c-115">En el ejemplo siguiente se muestra una llamada a un procedimiento sobrecargado `Sub` que produce este error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-115">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>

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

<span data-ttu-id="cfa0c-116">En el ejemplo anterior, si el compilador permitía la llamada a `s1` como escrita, la resolución se realizaría a través de la clase `c1` en lugar de la interfaz `i1` .</span><span class="sxs-lookup"><span data-stu-id="cfa0c-116">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="cfa0c-117">Esto significa que el compilador no tendría en cuenta `s2` porque su nombre es diferente en `c1` , aunque es la opción correcta tal y como se define en `i1` .</span><span class="sxs-lookup"><span data-stu-id="cfa0c-117">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>

<span data-ttu-id="cfa0c-118">Puede corregir el error cambiando la llamada a cualquiera de las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="cfa0c-118">You can correct the error by changing the call to either of the following lines of code:</span></span>

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

<span data-ttu-id="cfa0c-119">Cada una de las líneas de código anteriores convierte explícitamente la `Object` variable `o1` a uno de los tipos de parámetros definidos para las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="cfa0c-119">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfa0c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfa0c-120">See also</span></span>

- [<span data-ttu-id="cfa0c-121">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="cfa0c-121">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="cfa0c-122">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="cfa0c-122">Overload Resolution</span></span>](../../programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="cfa0c-123">CType Function</span><span class="sxs-lookup"><span data-stu-id="cfa0c-123">CType Function</span></span>](../functions/ctype-function.md)
