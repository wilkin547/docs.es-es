---
title: La expresión llama de forma recursiva a la propiedad contenedora '<propertyname>'
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: f5b8b226d46afa0555559de0930f20025ba27f2b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162770"
---
# <a name="bc42026-expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="5acca-102">BC42026: la expresión llama de forma recursiva a la propiedad contenedora ' \<propertyname> '</span><span class="sxs-lookup"><span data-stu-id="5acca-102">BC42026: Expression recursively calls the containing property '\<propertyname>'</span></span>

<span data-ttu-id="5acca-103">Una instrucción en el `Set` procedimiento de una definición de propiedad almacena un valor en el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5acca-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>

 <span data-ttu-id="5acca-104">El enfoque recomendado para contener el valor de una propiedad es definir una `Private` variable en el contenedor de la propiedad y utilizarla en los `Get` procedimientos y `Set` .</span><span class="sxs-lookup"><span data-stu-id="5acca-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="5acca-105">`Set`Después, el procedimiento debe almacenar el valor de entrada en esta `Private` variable.</span><span class="sxs-lookup"><span data-stu-id="5acca-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>

 <span data-ttu-id="5acca-106">El `Get` procedimiento se comporta como un `Function` procedimiento, por lo que puede asignar un valor al nombre de la propiedad y devolver el control al encontrar la `End Get` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5acca-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="5acca-107">Sin embargo, el enfoque recomendado consiste en incluir la `Private` variable como valor en una [instrucción return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5acca-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../statements/return-statement.md).</span></span>

 <span data-ttu-id="5acca-108">El `Set` procedimiento se comporta como un `Sub` procedimiento, que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="5acca-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="5acca-109">Por lo tanto, el nombre del procedimiento o de la propiedad no tiene ningún significado especial dentro de un `Set` procedimiento, y no se puede almacenar un valor en él.</span><span class="sxs-lookup"><span data-stu-id="5acca-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>

 <span data-ttu-id="5acca-110">En el ejemplo siguiente se muestra el enfoque que puede producir este error, seguido del enfoque recomendado.</span><span class="sxs-lookup"><span data-stu-id="5acca-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>

```vb
Public Class illustrateProperties
' The code in the following property causes this error.
    Public Property badProp() As Char
        Get
            Dim charValue As Char
            ' Insert code to update charValue.
            badProp = charValue
        End Get
        Set(ByVal Value As Char)
            ' The following statement causes this error.
            badProp = Value
            ' The value stored in the local variable badProp
            ' is not used by the Get procedure in this property.
        End Set
    End Property
' The following code uses the recommended approach.
    Private propValue As Char
    Public Property goodProp() As Char
        Get
            ' Insert code to update propValue.
            Return propValue
        End Get
        Set(ByVal Value As Char)
            propValue = Value
        End Set
    End Property
End Class
```

 <span data-ttu-id="5acca-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="5acca-111">By default, this message is a warning.</span></span> <span data-ttu-id="5acca-112">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5acca-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="5acca-113">**Identificador de error:** BC42026</span><span class="sxs-lookup"><span data-stu-id="5acca-113">**Error ID:** BC42026</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5acca-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5acca-114">To correct this error</span></span>

- <span data-ttu-id="5acca-115">Vuelva a escribir la definición de la propiedad para usar el enfoque recomendado, tal como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5acca-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>

## <a name="see-also"></a><span data-ttu-id="5acca-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5acca-116">See also</span></span>

- [<span data-ttu-id="5acca-117">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="5acca-117">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="5acca-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="5acca-118">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="5acca-119">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5acca-119">Set Statement</span></span>](../statements/set-statement.md)
