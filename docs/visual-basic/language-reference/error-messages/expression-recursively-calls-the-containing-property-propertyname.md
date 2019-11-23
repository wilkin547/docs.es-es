---
title: La expresión llama de forma recursiva a la propiedad contenedora '<propertyname>'
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698568"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="c008d-102">La expresión llama de forma recursiva a la propiedad contenedora '\<PropertyName > '</span><span class="sxs-lookup"><span data-stu-id="c008d-102">Expression recursively calls the containing property '\<propertyname>'</span></span>
<span data-ttu-id="c008d-103">Una instrucción en el procedimiento `Set` de una definición de propiedad almacena un valor en el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c008d-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="c008d-104">El enfoque recomendado para contener el valor de una propiedad es definir una variable `Private` en el contenedor de la propiedad y utilizarla en los procedimientos `Get` y `Set`.</span><span class="sxs-lookup"><span data-stu-id="c008d-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="c008d-105">A continuación, el procedimiento `Set` debe almacenar el valor entrante en esta variable `Private`.</span><span class="sxs-lookup"><span data-stu-id="c008d-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="c008d-106">El procedimiento `Get` se comporta como un procedimiento `Function`, por lo que puede asignar un valor al nombre de la propiedad y devolver el control al encontrar la instrucción `End Get`.</span><span class="sxs-lookup"><span data-stu-id="c008d-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="c008d-107">Sin embargo, el enfoque recomendado consiste en incluir la variable `Private` como valor en una [instrucción return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c008d-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="c008d-108">El procedimiento `Set` se comporta como un procedimiento `Sub`, que no devuelve ningún valor.</span><span class="sxs-lookup"><span data-stu-id="c008d-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="c008d-109">Por lo tanto, el nombre del procedimiento o de la propiedad no tiene ningún significado especial dentro de un procedimiento de `Set`, y no se puede almacenar un valor en él.</span><span class="sxs-lookup"><span data-stu-id="c008d-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="c008d-110">En el ejemplo siguiente se muestra el enfoque que puede producir este error, seguido del enfoque recomendado.</span><span class="sxs-lookup"><span data-stu-id="c008d-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
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
  
 <span data-ttu-id="c008d-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="c008d-111">By default, this message is a warning.</span></span> <span data-ttu-id="c008d-112">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c008d-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c008d-113">**Identificador de error:** BC42026</span><span class="sxs-lookup"><span data-stu-id="c008d-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c008d-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c008d-114">To correct this error</span></span>  
  
- <span data-ttu-id="c008d-115">Vuelva a escribir la definición de la propiedad para usar el enfoque recomendado, tal como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c008d-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c008d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c008d-116">See also</span></span>

- [<span data-ttu-id="c008d-117">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="c008d-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="c008d-118">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c008d-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="c008d-119">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c008d-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
