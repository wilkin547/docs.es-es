---
title: Procedimiento Controlar el ámbito de una Variable (Visual Basic)
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
ms.openlocfilehash: 24a7ae3b8f3400beeaedb20ea6352ea44bdb7597
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794737"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="f7ab1-102">Procedimiento Controlar el ámbito de una Variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7ab1-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="f7ab1-103">Normalmente, es una variable en *ámbito*, o visible como referencia, a lo largo de la región en la que se declara.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="f7ab1-104">En del algunos casos, la variable *nivel de acceso* puede influir en su ámbito.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="f7ab1-105">Para obtener más información, consulta [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="f7ab1-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="f7ab1-106">Ámbito en el nivel de procedimiento o bloque</span><span class="sxs-lookup"><span data-stu-id="f7ab1-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="f7ab1-107">Para hacer visible solo dentro de un bloque de una variable</span><span class="sxs-lookup"><span data-stu-id="f7ab1-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="f7ab1-108">Colocar el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) para la variable entre el inicio y finalización de instrucciones de declaración de ese bloque, por ejemplo entre el `For` y `Next` las instrucciones de un `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="f7ab1-109">Se puede hacer referencia a la variable solo desde dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="f7ab1-110">Para hacer que una variable sea visible solo dentro de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="f7ab1-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="f7ab1-111">Colocar el `Dim` instrucción para la variable dentro del procedimiento pero fuera de cualquier bloque (como un `With`... `End With` bloque).</span><span class="sxs-lookup"><span data-stu-id="f7ab1-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="f7ab1-112">Se puede hacer referencia a la variable solo desde dentro del procedimiento, incluso dentro de cualquier bloque contenido en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="f7ab1-113">Ámbito en el nivel de módulo o Namespace</span><span class="sxs-lookup"><span data-stu-id="f7ab1-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="f7ab1-114">Para mayor comodidad, el término único *nivel de módulo* se aplica igualmente a los módulos, clases y estructuras.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="f7ab1-115">El nivel de acceso de una variable de nivel de módulo determina su ámbito.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="f7ab1-116">El espacio de nombres que contiene el módulo, clase o estructura también influye en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="f7ab1-117">Para hacer visible a lo largo de un módulo, clase o estructura de una variable</span><span class="sxs-lookup"><span data-stu-id="f7ab1-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="f7ab1-118">Colocar el `Dim` instrucción para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f7ab1-119">Incluir el [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="f7ab1-120">Puede hacer referencia a la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de él.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="f7ab1-121">Para hacer visible a lo largo de un espacio de nombres de variable</span><span class="sxs-lookup"><span data-stu-id="f7ab1-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="f7ab1-122">Colocar el `Dim` instrucción para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f7ab1-123">Incluir el [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [pública](../../../../visual-basic/language-reference/modifiers/public.md) palabra clave en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="f7ab1-124">Puede hacer referencia a la variable desde cualquier lugar dentro del espacio de nombres que contiene el módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7ab1-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7ab1-125">Example</span></span>  
 <span data-ttu-id="f7ab1-126">El ejemplo siguiente declara una variable en el nivel de módulo y limita la visibilidad para el código dentro del módulo.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```  
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
  
 <span data-ttu-id="f7ab1-127">En el ejemplo anterior, todos los procedimientos definen en el módulo `demonstrateScope` puede hacer referencia a la `String` variable `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="f7ab1-128">Cuando el `usePrivateVariable` se llama al procedimiento, se muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="f7ab1-129">La siguiente modificación en el ejemplo anterior, la variable de cadena `strMsg` puede hacer referencia a código en cualquier lugar en el espacio de nombres de su declaración.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="f7ab1-130">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="f7ab1-130">Robust Programming</span></span>  
 <span data-ttu-id="f7ab1-131">El ámbito más restringido el de una variable, menos posibilidades que tendrá de hacer referencia accidentalmente a ella en lugar de otra variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="f7ab1-132">También puede minimizar los problemas de comparación de referencias.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f7ab1-133">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7ab1-133">.NET Framework Security</span></span>  
 <span data-ttu-id="f7ab1-134">Más estrecha del ámbito de una variable, cuantos menos las posibilidades de que código malintencionado puede hacer incorrecto usar del mismo.</span><span class="sxs-lookup"><span data-stu-id="f7ab1-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ab1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7ab1-135">See also</span></span>

- [<span data-ttu-id="f7ab1-136">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7ab1-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="f7ab1-137">Duración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7ab1-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="f7ab1-138">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7ab1-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f7ab1-139">Variables</span><span class="sxs-lookup"><span data-stu-id="f7ab1-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="f7ab1-140">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="f7ab1-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="f7ab1-141">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f7ab1-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
