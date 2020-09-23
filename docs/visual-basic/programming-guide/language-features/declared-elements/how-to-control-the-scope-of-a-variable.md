---
title: Procedimiento para controlar el ámbito de una variable
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 2ce7c1700eec54542719e6e0880466ca136e86f6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095438"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="68a72-102">Cómo: Controlar el ámbito de una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a72-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>

<span data-ttu-id="68a72-103">Normalmente, una variable está en el *ámbito*o es visible como referencia, en toda la región en la que se declara.</span><span class="sxs-lookup"><span data-stu-id="68a72-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="68a72-104">En algunos casos, el nivel de *acceso* de la variable puede influir en su ámbito.</span><span class="sxs-lookup"><span data-stu-id="68a72-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="68a72-105">Para obtener más información, consulta [Scope in Visual Basic](scope.md).</span><span class="sxs-lookup"><span data-stu-id="68a72-105">For more information, see [Scope in Visual Basic](scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="68a72-106">Ámbito en el nivel de bloque o procedimiento</span><span class="sxs-lookup"><span data-stu-id="68a72-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="68a72-107">Para hacer que una variable sea visible solo dentro de un bloque</span><span class="sxs-lookup"><span data-stu-id="68a72-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="68a72-108">Coloque la [instrucción Dim](../../../language-reference/statements/dim-statement.md) para la variable entre las instrucciones de declaración de inicio y finalización de ese bloque, por ejemplo, entre las `For` `Next` instrucciones y de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="68a72-108">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="68a72-109">Solo puede hacer referencia a la variable desde dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="68a72-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="68a72-110">Para hacer que una variable sea visible solo dentro de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="68a72-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="68a72-111">Coloque la `Dim` instrucción para la variable dentro del procedimiento pero fuera de cualquier bloque (como un `With` bloque... `End With` ).</span><span class="sxs-lookup"><span data-stu-id="68a72-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="68a72-112">Solo puede hacer referencia a la variable desde dentro del procedimiento, incluido dentro de cualquier bloque incluido en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="68a72-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="68a72-113">Ámbito en el nivel de módulo o espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="68a72-113">Scope at Module or Namespace Level</span></span>  

 <span data-ttu-id="68a72-114">Para mayor comodidad, el *nivel de módulo* de un solo término se aplica igualmente a los módulos, las clases y las estructuras.</span><span class="sxs-lookup"><span data-stu-id="68a72-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="68a72-115">El nivel de acceso de una variable de nivel de módulo determina su ámbito.</span><span class="sxs-lookup"><span data-stu-id="68a72-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="68a72-116">El espacio de nombres que contiene el módulo, la clase o la estructura también influye en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="68a72-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="68a72-117">Para hacer que una variable sea visible en todo un módulo, clase o estructura</span><span class="sxs-lookup"><span data-stu-id="68a72-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="68a72-118">Coloque la `Dim` instrucción para la variable dentro del módulo, la clase o la estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="68a72-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="68a72-119">Incluya la palabra clave [Private](../../../language-reference/modifiers/private.md) en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="68a72-119">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="68a72-120">Puede hacer referencia a la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de ella.</span><span class="sxs-lookup"><span data-stu-id="68a72-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="68a72-121">Para hacer que una variable sea visible en todo un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="68a72-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="68a72-122">Coloque la `Dim` instrucción para la variable dentro del módulo, la clase o la estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="68a72-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="68a72-123">Incluya la palabra clave [Friend](../../../language-reference/modifiers/friend.md) o [Public](../../../language-reference/modifiers/public.md) en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="68a72-123">Include the [Friend](../../../language-reference/modifiers/friend.md) or [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="68a72-124">Puede hacer referencia a la variable desde cualquier lugar dentro del espacio de nombres que contiene el módulo, la clase o la estructura.</span><span class="sxs-lookup"><span data-stu-id="68a72-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a72-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68a72-125">Example</span></span>  

 <span data-ttu-id="68a72-126">En el ejemplo siguiente se declara una variable en el nivel de módulo y se limita su visibilidad al código dentro del módulo.</span><span class="sxs-lookup"><span data-stu-id="68a72-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="68a72-127">En el ejemplo anterior, todos los procedimientos definidos en Module `demonstrateScope` pueden hacer referencia a la `String` variable `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="68a72-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="68a72-128">Cuando `usePrivateVariable` se llama al procedimiento, se muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="68a72-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="68a72-129">Con la siguiente modificación en el ejemplo anterior, el código puede hacer referencia a la variable de cadena `strMsg` en cualquier lugar del espacio de nombres de su declaración.</span><span class="sxs-lookup"><span data-stu-id="68a72-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="68a72-130">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="68a72-130">Robust Programming</span></span>  

 <span data-ttu-id="68a72-131">Cuanto más estrecho sea el ámbito de una variable, menos oportunidades tendrá para hacer referencia accidentalmente a ella en lugar de a otra variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="68a72-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="68a72-132">También puede minimizar los problemas de coincidencia de referencias.</span><span class="sxs-lookup"><span data-stu-id="68a72-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="68a72-133">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="68a72-133">.NET Framework Security</span></span>  

 <span data-ttu-id="68a72-134">Cuanto más estrecho sea el ámbito de una variable, menor será la probabilidad de que el código malintencionado pueda hacer un uso inadecuado de ella.</span><span class="sxs-lookup"><span data-stu-id="68a72-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a72-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="68a72-135">See also</span></span>

- [<span data-ttu-id="68a72-136">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68a72-136">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="68a72-137">Período de duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68a72-137">Lifetime in Visual Basic</span></span>](lifetime.md)
- [<span data-ttu-id="68a72-138">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68a72-138">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="68a72-139">Variables</span><span class="sxs-lookup"><span data-stu-id="68a72-139">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="68a72-140">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="68a72-140">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="68a72-141">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="68a72-141">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
