---
title: Procedimiento Acceder a una variable oculta por una clase derivada (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 68f92142cdc435ebd82101eea83035e1d09dcf25
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630012"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="9b75e-102">Procedimiento Acceder a una variable oculta por una clase derivada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b75e-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>

<span data-ttu-id="9b75e-103">Cuando el código de una clase derivada tiene acceso a una variable, el compilador resuelve normalmente la referencia a la versión accesible más cercana, es decir, a la versión accesible el menor paso de derivación hacia atrás desde la clase de acceso.</span><span class="sxs-lookup"><span data-stu-id="9b75e-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="9b75e-104">Si la variable se define en la clase derivada, el código normalmente accede a esa definición.</span><span class="sxs-lookup"><span data-stu-id="9b75e-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>

<span data-ttu-id="9b75e-105">Si la variable de clase derivada sombrea una variable de la clase base, oculta la versión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="9b75e-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="9b75e-106">Sin embargo, puede tener acceso a la variable de clase base mediante la calificación `MyBase` de la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="9b75e-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="9b75e-107">Para tener acceso a una variable de clase base oculta por una clase derivada</span><span class="sxs-lookup"><span data-stu-id="9b75e-107">To access a base class variable hidden by a derived class</span></span>

- <span data-ttu-id="9b75e-108">En una expresión o instrucción de asignación, anteponga a la `MyBase` palabra clave y un punto (`.`) el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="9b75e-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>

    <span data-ttu-id="9b75e-109">El compilador resuelve la referencia a la versión de la clase base de la variable.</span><span class="sxs-lookup"><span data-stu-id="9b75e-109">The compiler resolves the reference to the base class version of the variable.</span></span>

    <span data-ttu-id="9b75e-110">En el ejemplo siguiente se ilustra el sombreado a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="9b75e-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="9b75e-111">Hace dos referencias, una que tiene acceso a la variable de sombreado y otra que omite el sombreado.</span><span class="sxs-lookup"><span data-stu-id="9b75e-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="9b75e-112">En el ejemplo anterior se declara la `shadowString` variable en la clase base y se sombrea en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9b75e-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="9b75e-113">El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el `shadowString` nombre no está calificado.</span><span class="sxs-lookup"><span data-stu-id="9b75e-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="9b75e-114">A continuación, muestra la versión sombreada `shadowString` cuando se califica con `MyBase` la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="9b75e-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="9b75e-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9b75e-115">Robust Programming</span></span>

<span data-ttu-id="9b75e-116">Para reducir el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra, puede calificar totalmente todas las referencias a una variable de la que se ha realizado una copia sombra.</span><span class="sxs-lookup"><span data-stu-id="9b75e-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="9b75e-117">La sombra introduce más de una versión de una variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9b75e-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="9b75e-118">Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="9b75e-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="9b75e-119">Esto puede aumentar el riesgo de hacer referencia a la versión incorrecta de la variable.</span><span class="sxs-lookup"><span data-stu-id="9b75e-119">This can increase the risk of referring to the wrong version of the variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b75e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b75e-120">See also</span></span>

- [<span data-ttu-id="9b75e-121">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="9b75e-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="9b75e-122">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b75e-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="9b75e-123">Diferencias entre sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="9b75e-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="9b75e-124">Cómo: Ocultar una variable con el mismo nombre que la variable</span><span class="sxs-lookup"><span data-stu-id="9b75e-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="9b75e-125">Procedimientos: Ocultar una variable heredada</span><span class="sxs-lookup"><span data-stu-id="9b75e-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="9b75e-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="9b75e-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="9b75e-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="9b75e-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="9b75e-128">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="9b75e-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="9b75e-129">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="9b75e-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
