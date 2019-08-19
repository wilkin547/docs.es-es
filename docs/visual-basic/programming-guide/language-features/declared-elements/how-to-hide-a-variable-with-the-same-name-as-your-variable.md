---
title: Procedimiento Ocultar una variable con el mismo nombre que la variable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 487e0a15ba6b52f92ab39fe0bae4ab15fa92707f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629988"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="59dc5-102">Procedimiento Ocultar una variable con el mismo nombre que la variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59dc5-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="59dc5-103">Puede ocultar una variable mediante la *sombra* , es decir, si la vuelve a definir con una variable del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="59dc5-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="59dc5-104">Puede sombrear la variable que desea ocultar de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="59dc5-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="59dc5-105">**Sombreado a través del ámbito.**</span><span class="sxs-lookup"><span data-stu-id="59dc5-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="59dc5-106">Puede prevalecer en el ámbito si lo redeclara dentro de una subregión de la región que contiene la variable que desea ocultar.</span><span class="sxs-lookup"><span data-stu-id="59dc5-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="59dc5-107">**Sombrear a través de la herencia.**</span><span class="sxs-lookup"><span data-stu-id="59dc5-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="59dc5-108">Si la variable que desea ocultar se define en el nivel de clase, puede sombrearla a través de la herencia si la redeclara con la palabra clave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="59dc5-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="59dc5-109">Dos maneras de ocultar una variable</span><span class="sxs-lookup"><span data-stu-id="59dc5-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="59dc5-110">Para ocultar una variable mediante su sombreado a través del ámbito</span><span class="sxs-lookup"><span data-stu-id="59dc5-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="59dc5-111">Determine la región que define la variable que desea ocultar y determine la subregión en la que se va a volver a definir con la variable.</span><span class="sxs-lookup"><span data-stu-id="59dc5-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="59dc5-112">Región de la variable</span><span class="sxs-lookup"><span data-stu-id="59dc5-112">Variable's region</span></span>|<span data-ttu-id="59dc5-113">Subregión permitida para redefinirla</span><span class="sxs-lookup"><span data-stu-id="59dc5-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="59dc5-114">Module</span><span class="sxs-lookup"><span data-stu-id="59dc5-114">Module</span></span>|<span data-ttu-id="59dc5-115">Una clase dentro del módulo</span><span class="sxs-lookup"><span data-stu-id="59dc5-115">A class within the module</span></span>|
    |<span data-ttu-id="59dc5-116">Clase</span><span class="sxs-lookup"><span data-stu-id="59dc5-116">Class</span></span>|<span data-ttu-id="59dc5-117">Una subclase dentro de la clase</span><span class="sxs-lookup"><span data-stu-id="59dc5-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="59dc5-118">Un procedimiento dentro de la clase</span><span class="sxs-lookup"><span data-stu-id="59dc5-118">A procedure within the class</span></span>|

    <span data-ttu-id="59dc5-119">No se puede volver a definir una variable de procedimiento en un bloque dentro de ese procedimiento `If`, por ejemplo, en... `End If` construcción`For` o bucle.</span><span class="sxs-lookup"><span data-stu-id="59dc5-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="59dc5-120">Cree la subregión si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="59dc5-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="59dc5-121">Dentro de la subregión, escriba una [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) que declare la variable de sombreado.</span><span class="sxs-lookup"><span data-stu-id="59dc5-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="59dc5-122">Cuando el código dentro de la subregión hace referencia al nombre de variable, el compilador resuelve la referencia a la variable de sombreado.</span><span class="sxs-lookup"><span data-stu-id="59dc5-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="59dc5-123">En el ejemplo siguiente se muestra el sombreado a través del ámbito, así como una referencia que omite el sombreado.</span><span class="sxs-lookup"><span data-stu-id="59dc5-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

    ```vb
    Module shadowByScope
        ' The following statement declares num as a module-level variable.
        Public num As Integer
        Sub show()
            ' The following statement declares num as a local variable.
            Dim num As Integer
            ' The following statement sets the value of the local variable.
            num = 2
            ' The following statement displays the module-level variable.
            MsgBox(CStr(shadowByScope.num))
        End Sub
        Sub useModuleLevelNum()
            ' The following statement sets the value of the module-level variable.
            num = 1
            show()
        End Sub
    End Module
    ```

    <span data-ttu-id="59dc5-124">En el ejemplo anterior se declara la `num` variable en el nivel de módulo y en el nivel de procedimiento `show`(en el procedimiento).</span><span class="sxs-lookup"><span data-stu-id="59dc5-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="59dc5-125">La variable `num` local prevalece sobre la variable `num` de nivel de `show`módulo en, por lo que la variable local se establece en 2.</span><span class="sxs-lookup"><span data-stu-id="59dc5-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="59dc5-126">Sin embargo, no hay ninguna variable local para `num` la sombra `useModuleLevelNum` en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="59dc5-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="59dc5-127">Por lo `useModuleLevelNum` tanto, establece el valor de la variable de nivel de módulo en 1.</span><span class="sxs-lookup"><span data-stu-id="59dc5-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="59dc5-128">La `MsgBox` llamada dentro `show` de omite el mecanismo de sombreado mediante la `num` calificación del nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="59dc5-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="59dc5-129">Por lo tanto, se muestra la variable de nivel de módulo en lugar de la variable local.</span><span class="sxs-lookup"><span data-stu-id="59dc5-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="59dc5-130">Ocultar una variable mediante su sombreado a través de la herencia</span><span class="sxs-lookup"><span data-stu-id="59dc5-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="59dc5-131">Asegúrese de que la variable que desea ocultar está declarada en una clase y en el nivel de clase (fuera de cualquier procedimiento).</span><span class="sxs-lookup"><span data-stu-id="59dc5-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="59dc5-132">De lo contrario, no puede sombrearla a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="59dc5-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="59dc5-133">Defina una clase derivada de la clase de la variable si aún no existe una.</span><span class="sxs-lookup"><span data-stu-id="59dc5-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="59dc5-134">Dentro de la clase derivada, escriba `Dim` una instrucción que declare la variable.</span><span class="sxs-lookup"><span data-stu-id="59dc5-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="59dc5-135">Incluya la palabra clave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) en la declaración.</span><span class="sxs-lookup"><span data-stu-id="59dc5-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="59dc5-136">Cuando el código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="59dc5-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="59dc5-137">En el ejemplo siguiente se ilustra el sombreado a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="59dc5-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="59dc5-138">Hace dos referencias, una que tiene acceso a la variable de sombreado y otra que omite el sombreado.</span><span class="sxs-lookup"><span data-stu-id="59dc5-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

    ```vb
    Public Class shadowBaseClass
        Public shadowString As String = "This is the base class string."
    End Class
    Public Class shadowDerivedClass
        Inherits shadowBaseClass
        Public Shadows shadowString As String = "This is the derived class string."
        Public Sub showStrings()
            Dim s As String = "Unqualified shadowString: " & shadowString &
                 vbCrLf & "MyBase.shadowString: " & MyBase.shadowString
            MsgBox(s)
        End Sub
    End Class
    ```

    <span data-ttu-id="59dc5-139">En el ejemplo anterior se declara la `shadowString` variable en la clase base y se sombrea en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="59dc5-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="59dc5-140">El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el `shadowString` nombre no está calificado.</span><span class="sxs-lookup"><span data-stu-id="59dc5-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="59dc5-141">A continuación, muestra la versión sombreada `shadowString` cuando se califica con `MyBase` la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="59dc5-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="59dc5-142">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="59dc5-142">Robust Programming</span></span>

<span data-ttu-id="59dc5-143">La sombra introduce más de una versión de una variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="59dc5-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="59dc5-144">Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="59dc5-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="59dc5-145">Esto puede aumentar el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra.</span><span class="sxs-lookup"><span data-stu-id="59dc5-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="59dc5-146">Puede reducir este riesgo calificando por completo todas las referencias a una variable de la que se ha realizado una copia sombra.</span><span class="sxs-lookup"><span data-stu-id="59dc5-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="59dc5-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="59dc5-147">See also</span></span>

- [<span data-ttu-id="59dc5-148">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="59dc5-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="59dc5-149">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59dc5-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="59dc5-150">Diferencias entre sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="59dc5-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="59dc5-151">Procedimientos: Ocultar una variable heredada</span><span class="sxs-lookup"><span data-stu-id="59dc5-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="59dc5-152">Procedimientos: Acceder a una variable oculta por una clase derivada</span><span class="sxs-lookup"><span data-stu-id="59dc5-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="59dc5-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="59dc5-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="59dc5-154">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="59dc5-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="59dc5-155">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="59dc5-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
