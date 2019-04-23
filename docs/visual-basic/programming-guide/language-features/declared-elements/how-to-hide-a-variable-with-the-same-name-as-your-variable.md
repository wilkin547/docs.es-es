---
title: Procedimiento Ocultar una Variable con el mismo nombre que su Variable (Visual Basic)
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
ms.openlocfilehash: 744c7aed50690d5591d1e8248e121cb66ef39108
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296191"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="37f18-102">Procedimiento Ocultar una Variable con el mismo nombre que su Variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37f18-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="37f18-103">Puede ocultar una variable por *sombrear* él, es decir, si se redefine con una variable del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="37f18-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="37f18-104">Puede reemplazar la variable que desea ocultar de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="37f18-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
-   <span data-ttu-id="37f18-105">**Sombreado por ámbito.**</span><span class="sxs-lookup"><span data-stu-id="37f18-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="37f18-106">Puede ocultar a través de ámbito por si vuelve a declarar dentro de una subregión de la región que contiene la variable que desea ocultar.</span><span class="sxs-lookup"><span data-stu-id="37f18-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
-   <span data-ttu-id="37f18-107">**Sombreado por herencia.**</span><span class="sxs-lookup"><span data-stu-id="37f18-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="37f18-108">Si la variable que desea ocultar se define en el nivel de clase, puede reemplazar mediante herencia volviéndola a declarar con la [sombras](../../../../visual-basic/language-reference/modifiers/shadows.md) palabra clave en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="37f18-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="37f18-109">Dos maneras para ocultar una Variable</span><span class="sxs-lookup"><span data-stu-id="37f18-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="37f18-110">Para ocultar una variable por él sombreado por ámbito</span><span class="sxs-lookup"><span data-stu-id="37f18-110">To hide a variable by shadowing it through scope</span></span>  
  
1. <span data-ttu-id="37f18-111">Determinar la región en la definición de la variable que desee ocultar y determine una subregión en la que se va a volver a definirlo con la variable.</span><span class="sxs-lookup"><span data-stu-id="37f18-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="37f18-112">Región de la variable</span><span class="sxs-lookup"><span data-stu-id="37f18-112">Variable's region</span></span>|<span data-ttu-id="37f18-113">Subregión permitida para volverla a definir</span><span class="sxs-lookup"><span data-stu-id="37f18-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="37f18-114">Module</span><span class="sxs-lookup"><span data-stu-id="37f18-114">Module</span></span>|<span data-ttu-id="37f18-115">Una clase dentro del módulo</span><span class="sxs-lookup"><span data-stu-id="37f18-115">A class within the module</span></span>|  
    |<span data-ttu-id="37f18-116">Clase</span><span class="sxs-lookup"><span data-stu-id="37f18-116">Class</span></span>|<span data-ttu-id="37f18-117">Una subclase dentro de la clase</span><span class="sxs-lookup"><span data-stu-id="37f18-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="37f18-118">Un procedimiento dentro de la clase</span><span class="sxs-lookup"><span data-stu-id="37f18-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="37f18-119">No se puede definir una variable de procedimiento en un bloque dentro de ese procedimiento, por ejemplo en un `If`... `End If` construcción o `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="37f18-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2. <span data-ttu-id="37f18-120">Cree la subregión si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="37f18-120">Create the subregion if it does not already exist.</span></span>  
  
3. <span data-ttu-id="37f18-121">Dentro de la subregión, escribir un [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) declarar la variable de sombreado.</span><span class="sxs-lookup"><span data-stu-id="37f18-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="37f18-122">Cuando el código de la subregión hace referencia al nombre de variable, el compilador resuelve la referencia a la variable de sombreado.</span><span class="sxs-lookup"><span data-stu-id="37f18-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="37f18-123">El ejemplo siguiente ilustra el sombreado por ámbito, así como una referencia que omite el sombreado.</span><span class="sxs-lookup"><span data-stu-id="37f18-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="37f18-124">El ejemplo anterior declara la variable `num` tanto a nivel de módulo en el nivel de procedimiento (en el procedimiento `show`).</span><span class="sxs-lookup"><span data-stu-id="37f18-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="37f18-125">La variable local `num` oculta o prevalece sobre la variable de nivel de módulo `num` en `show`, por lo que la variable local se establece en 2.</span><span class="sxs-lookup"><span data-stu-id="37f18-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="37f18-126">Sin embargo, no hay ninguna variable local para instantáneas `num` en el `useModuleLevelNum` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="37f18-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="37f18-127">Por lo tanto, `useModuleLevelNum` establece el valor de la variable de nivel de módulo en 1.</span><span class="sxs-lookup"><span data-stu-id="37f18-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="37f18-128">El `MsgBox` volat `show` omite el mecanismo de sombreado calificando `num` con el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="37f18-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="37f18-129">Por lo tanto, muestra la variable de nivel de módulo en lugar de la variable local.</span><span class="sxs-lookup"><span data-stu-id="37f18-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="37f18-130">Para ocultar una variable por él sombreado por herencia</span><span class="sxs-lookup"><span data-stu-id="37f18-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1. <span data-ttu-id="37f18-131">Asegúrese de que la variable que desea ocultar está declarada en una clase y en el nivel de clase (fuera de cualquier procedimiento).</span><span class="sxs-lookup"><span data-stu-id="37f18-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="37f18-132">En caso contrario, no puede prevalecer mediante herencia.</span><span class="sxs-lookup"><span data-stu-id="37f18-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2. <span data-ttu-id="37f18-133">Defina una clase derivada de la clase de la variable si no existe.</span><span class="sxs-lookup"><span data-stu-id="37f18-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3. <span data-ttu-id="37f18-134">Dentro de la clase derivada, escribe un `Dim` instrucción declara la variable.</span><span class="sxs-lookup"><span data-stu-id="37f18-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="37f18-135">Incluir el [sombras](../../../../visual-basic/language-reference/modifiers/shadows.md) palabra clave en la declaración.</span><span class="sxs-lookup"><span data-stu-id="37f18-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="37f18-136">Cuando el código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="37f18-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="37f18-137">El ejemplo siguiente ilustra el sombreado por herencia.</span><span class="sxs-lookup"><span data-stu-id="37f18-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="37f18-138">Hace que dos referencias, uno que tiene acceso a la variable de sombreado y otro que omite el sombreado.</span><span class="sxs-lookup"><span data-stu-id="37f18-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="37f18-139">El ejemplo anterior declara la variable `shadowString` en la clase base y lo reemplaza en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="37f18-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="37f18-140">El procedimiento `showStrings` en la clase derivada, muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.</span><span class="sxs-lookup"><span data-stu-id="37f18-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="37f18-141">A continuación, muestra la versión sombreada cuando `shadowString` se califica con el `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="37f18-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="37f18-142">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="37f18-142">Robust Programming</span></span>  
 <span data-ttu-id="37f18-143">El sombreado presenta más de una versión de una variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="37f18-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="37f18-144">Cuando una instrucción de código hace referencia al nombre de variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="37f18-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="37f18-145">Esto puede aumentar el riesgo de que hace referencia a una versión no deseada de una variable sombreada.</span><span class="sxs-lookup"><span data-stu-id="37f18-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="37f18-146">Puede reducir este riesgo si califica completamente todas las referencias a una variable sombreada.</span><span class="sxs-lookup"><span data-stu-id="37f18-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f18-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f18-147">See also</span></span>

- [<span data-ttu-id="37f18-148">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="37f18-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="37f18-149">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37f18-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="37f18-150">Diferencias entre sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="37f18-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="37f18-151">Cómo: Ocultar una Variable heredada</span><span class="sxs-lookup"><span data-stu-id="37f18-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="37f18-152">Cómo: Obtener acceso a una Variable que oculta una clase derivada</span><span class="sxs-lookup"><span data-stu-id="37f18-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="37f18-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="37f18-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="37f18-154">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="37f18-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="37f18-155">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="37f18-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
