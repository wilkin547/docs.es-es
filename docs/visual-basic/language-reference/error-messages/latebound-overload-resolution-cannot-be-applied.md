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
ms.openlocfilehash: 4500a177c7a4729fe5131af1b007fd38e77afe07
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397342"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="ab902-102">La resolución de sobrecarga enlazada tardíamente no se puede aplicar a '\<procedurename>' porque la instancia de acceso es un tipo de interfaz</span><span class="sxs-lookup"><span data-stu-id="ab902-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>

<span data-ttu-id="ab902-103">El compilador está intentando resolver una referencia a una propiedad o procedimiento sobrecargado, pero se produce un error en la referencia porque un argumento es de tipo `Object` y el objeto de referencia tiene el tipo de datos de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ab902-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="ab902-104">El `Object` argumento obliga al compilador a resolver la referencia como enlazada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ab902-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>

<span data-ttu-id="ab902-105">En estas circunstancias, el compilador resuelve la sobrecarga a través de la clase de implementación en lugar de a través de la interfaz subyacente.</span><span class="sxs-lookup"><span data-stu-id="ab902-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="ab902-106">Si la clase cambia el nombre de una de las versiones sobrecargadas, el compilador no considera que la versión es una sobrecarga porque su nombre es diferente.</span><span class="sxs-lookup"><span data-stu-id="ab902-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="ab902-107">Esto, a su vez, hace que el compilador omita la versión a la que se ha cambiado el nombre cuando podría haber sido la opción correcta para resolver la referencia.</span><span class="sxs-lookup"><span data-stu-id="ab902-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>

<span data-ttu-id="ab902-108">**Identificador de error:** BC30933</span><span class="sxs-lookup"><span data-stu-id="ab902-108">**Error ID:** BC30933</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ab902-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ab902-109">To correct this error</span></span>

- <span data-ttu-id="ab902-110">Use `CType` para convertir el argumento de `Object` en el tipo especificado por la firma de la sobrecarga a la que desea llamar.</span><span class="sxs-lookup"><span data-stu-id="ab902-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>

  <span data-ttu-id="ab902-111">Tenga en cuenta que no ayuda a convertir el objeto que hace referencia en la interfaz subyacente.</span><span class="sxs-lookup"><span data-stu-id="ab902-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="ab902-112">Debe convertir el argumento para evitar este error.</span><span class="sxs-lookup"><span data-stu-id="ab902-112">You must cast the argument to avoid this error.</span></span>

## <a name="example"></a><span data-ttu-id="ab902-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab902-113">Example</span></span>

<span data-ttu-id="ab902-114">En el ejemplo siguiente se muestra una llamada a un procedimiento sobrecargado `Sub` que produce este error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="ab902-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>

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

<span data-ttu-id="ab902-115">En el ejemplo anterior, si el compilador permitía la llamada a `s1` como escrita, la resolución se realizaría a través de la clase `c1` en lugar de la interfaz `i1` .</span><span class="sxs-lookup"><span data-stu-id="ab902-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="ab902-116">Esto significa que el compilador no tendría en cuenta `s2` porque su nombre es diferente en `c1` , aunque es la opción correcta tal y como se define en `i1` .</span><span class="sxs-lookup"><span data-stu-id="ab902-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>

<span data-ttu-id="ab902-117">Puede corregir el error cambiando la llamada a cualquiera de las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="ab902-117">You can correct the error by changing the call to either of the following lines of code:</span></span>

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

<span data-ttu-id="ab902-118">Cada una de las líneas de código anteriores convierte explícitamente la `Object` variable `o1` a uno de los tipos de parámetros definidos para las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="ab902-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab902-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab902-119">See also</span></span>

- [<span data-ttu-id="ab902-120">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="ab902-120">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="ab902-121">Resolución de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ab902-121">Overload Resolution</span></span>](../../programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="ab902-122">CType Function</span><span class="sxs-lookup"><span data-stu-id="ab902-122">CType Function</span></span>](../functions/ctype-function.md)
