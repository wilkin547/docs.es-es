---
title: "La expresión llama recursivamente la propiedad contenedora &#39; &lt;propertyname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47de3c2d25336962168f01a4c8717274de7c9aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="8cf78-102">La expresión llama recursivamente la propiedad contenedora &#39; &lt;propertyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="8cf78-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="8cf78-103">Una instrucción en el `Set` procedimiento con una definición de propiedad almacena un valor en el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8cf78-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="8cf78-104">El enfoque recomendado para conservar el valor de una propiedad consiste en definir un `Private` variable al contenedor de propiedades y utilizar tanto en el `Get` y `Set` procedimientos.</span><span class="sxs-lookup"><span data-stu-id="8cf78-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="8cf78-105">El `Set` procedimiento, a continuación, debe almacenar el valor de entrada en este `Private` variable.</span><span class="sxs-lookup"><span data-stu-id="8cf78-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="8cf78-106">El `Get` procedimiento se comporta como un `Function` procedimiento, por lo que puede asignar un valor al nombre de propiedad y devolver el control cuando se encuentra el `End Get` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8cf78-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="8cf78-107">Sin embargo, es el enfoque recomendado, debe incluir el `Private` variable como el valor de un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8cf78-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="8cf78-108">El `Set` procedimiento se comporta como un `Sub` procedimiento, que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="8cf78-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="8cf78-109">Por lo tanto, el nombre de procedimiento o una propiedad no tiene ningún significado especial dentro de un `Set` procedimiento y no se puede almacenar un valor en él.</span><span class="sxs-lookup"><span data-stu-id="8cf78-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="8cf78-110">En el ejemplo siguiente se muestra el enfoque que puede producir este error, seguido por el enfoque recomendado.</span><span class="sxs-lookup"><span data-stu-id="8cf78-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```  
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
  
 <span data-ttu-id="8cf78-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="8cf78-111">By default, this message is a warning.</span></span> <span data-ttu-id="8cf78-112">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8cf78-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8cf78-113">**Id. de error:** BC42026</span><span class="sxs-lookup"><span data-stu-id="8cf78-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8cf78-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8cf78-114">To correct this error</span></span>  
  
-   <span data-ttu-id="8cf78-115">Vuelva a escribir la definición de propiedad para utilizar el enfoque recomendado como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="8cf78-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf78-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cf78-116">See Also</span></span>  
 [<span data-ttu-id="8cf78-117">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="8cf78-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="8cf78-118">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8cf78-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="8cf78-119">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8cf78-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
