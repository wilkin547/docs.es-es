---
description: "Más información acerca de: BC42110: el tipo de la variable ' <variablename> ' no se inferirá porque está enlazado a un campo en un ámbito de inclusión"
title: El tipo de la variable '<variablename>' no se inferirá porque está enlazado a un campo en un ámbito de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: db31f1a6e87a2fd133f095e2fbdde7bc6bded97e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641244"
---
# <a name="bc42110-the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="7c032-103">BC42110: el tipo de la variable ' \<variablename> ' no se inferirá porque está enlazado a un campo en un ámbito de inclusión</span><span class="sxs-lookup"><span data-stu-id="7c032-103">BC42110: The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="7c032-104">El tipo de la variable ' \<variablename> ' no se inferirá porque está enlazado a un campo en un ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="7c032-104">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="7c032-105">Cambie el nombre de ' \<variablename> ' o use el nombre completo (por ejemplo, ' me. variablename ' o ' MyBase. variablename ').</span><span class="sxs-lookup"><span data-stu-id="7c032-105">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="7c032-106">Una variable de control de bucle en su código tiene el mismo nombre que un campo de la clase u otro ámbito de inclusión.</span><span class="sxs-lookup"><span data-stu-id="7c032-106">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="7c032-107">Dado que la variable de control se utiliza sin una cláusula `As`, se enlaza al campo en el ámbito de inclusión y el compilador no crea una nueva variable para ella ni infiere su tipo.</span><span class="sxs-lookup"><span data-stu-id="7c032-107">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="7c032-108">En el ejemplo siguiente, `Index`, es decir, la variable de control en la instrucción `For`, se enlaza al campo `Index` de la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="7c032-108">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="7c032-109">El compilador no crea una nueva variable para la variable de control `Index` ni infiere su tipo.</span><span class="sxs-lookup"><span data-stu-id="7c032-109">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

<span data-ttu-id="7c032-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="7c032-110">By default, this message is a warning.</span></span> <span data-ttu-id="7c032-111">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7c032-111">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="7c032-112">**Identificador de error:** BC42110</span><span class="sxs-lookup"><span data-stu-id="7c032-112">**Error ID:** BC42110</span></span>

## <a name="to-address-this-warning"></a><span data-ttu-id="7c032-113">Para resolver esta advertencia</span><span class="sxs-lookup"><span data-stu-id="7c032-113">To address this warning</span></span>

- <span data-ttu-id="7c032-114">Convierta la variable de control de bucle en local cambiando su nombre por un identificador que tampoco sea el nombre de un campo de la clase.</span><span class="sxs-lookup"><span data-stu-id="7c032-114">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="7c032-115">Asegúrese de que la variable de control de bucle se enlaza al campo de clase agregando el prefijo `Me.` al nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="7c032-115">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="7c032-116">En lugar de basarse en la inferencia de tipo local, use una cláusula `As` para especificar un tipo para la variable de control de bucle.</span><span class="sxs-lookup"><span data-stu-id="7c032-116">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="7c032-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c032-117">Example</span></span>

 <span data-ttu-id="7c032-118">El código siguiente muestra el ejemplo anterior con la primera corrección en contexto.</span><span class="sxs-lookup"><span data-stu-id="7c032-118">The following code shows the earlier example with the first correction in place.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="7c032-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c032-119">See also</span></span>

- [<span data-ttu-id="7c032-120">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7c032-120">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="7c032-121">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="7c032-121">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="7c032-122">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="7c032-122">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="7c032-123">Procedimiento para hacer referencia a la instancia actual de un objeto</span><span class="sxs-lookup"><span data-stu-id="7c032-123">How to: Refer to the Current Instance of an Object</span></span>](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="7c032-124">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="7c032-124">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="7c032-125">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="7c032-125">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
