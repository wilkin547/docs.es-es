---
description: 'Más información sobre: Cómo: obtener acceso a una variable oculta por una clase derivada (Visual Basic)'
title: Procedimiento para obtener acceso a una variable que se encuentra oculta por una clase derivada
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 5ac1dd8afc8c32c91b748c8316d035d69468d887
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430058"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="b3419-103">Cómo: Obtener acceso a una variable que oculta una clase derivada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3419-103">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>

<span data-ttu-id="b3419-104">Cuando el código de una clase derivada tiene acceso a una variable, el compilador resuelve normalmente la referencia a la versión accesible más cercana, es decir, a la versión accesible el menor paso de derivación hacia atrás desde la clase de acceso.</span><span class="sxs-lookup"><span data-stu-id="b3419-104">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="b3419-105">Si la variable se define en la clase derivada, el código normalmente accede a esa definición.</span><span class="sxs-lookup"><span data-stu-id="b3419-105">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>

<span data-ttu-id="b3419-106">Si la variable de clase derivada sombrea una variable de la clase base, oculta la versión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="b3419-106">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="b3419-107">Sin embargo, puede tener acceso a la variable de clase base mediante la calificación de la `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b3419-107">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="b3419-108">Para tener acceso a una variable de clase base oculta por una clase derivada</span><span class="sxs-lookup"><span data-stu-id="b3419-108">To access a base class variable hidden by a derived class</span></span>

- <span data-ttu-id="b3419-109">En una expresión o instrucción de asignación, anteponga a la `MyBase` palabra clave y un punto () el nombre de la variable `.` .</span><span class="sxs-lookup"><span data-stu-id="b3419-109">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>

    <span data-ttu-id="b3419-110">El compilador resuelve la referencia a la versión de la clase base de la variable.</span><span class="sxs-lookup"><span data-stu-id="b3419-110">The compiler resolves the reference to the base class version of the variable.</span></span>

    <span data-ttu-id="b3419-111">En el ejemplo siguiente se ilustra el sombreado a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="b3419-111">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="b3419-112">Hace dos referencias, una que tiene acceso a la variable de sombreado y otra que omite el sombreado.</span><span class="sxs-lookup"><span data-stu-id="b3419-112">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="b3419-113">En el ejemplo anterior se declara la variable `shadowString` en la clase base y se sombrea en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="b3419-113">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="b3419-114">El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.</span><span class="sxs-lookup"><span data-stu-id="b3419-114">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="b3419-115">A continuación, muestra la versión sombreada cuando `shadowString` se califica con la `MyBase`  palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b3419-115">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="b3419-116">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b3419-116">Robust Programming</span></span>

<span data-ttu-id="b3419-117">Para reducir el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra, puede calificar totalmente todas las referencias a una variable de la que se ha realizado una copia sombra.</span><span class="sxs-lookup"><span data-stu-id="b3419-117">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="b3419-118">La sombra introduce más de una versión de una variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b3419-118">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="b3419-119">Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="b3419-119">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="b3419-120">Esto puede aumentar el riesgo de hacer referencia a la versión incorrecta de la variable.</span><span class="sxs-lookup"><span data-stu-id="b3419-120">This can increase the risk of referring to the wrong version of the variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3419-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3419-121">See also</span></span>

- [<span data-ttu-id="b3419-122">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="b3419-122">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="b3419-123">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3419-123">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="b3419-124">Diferencias entre sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="b3419-124">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="b3419-125">Procedimiento para ocultar una variable con el mismo nombre que su variable</span><span class="sxs-lookup"><span data-stu-id="b3419-125">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="b3419-126">Procedimiento para ocultar una variable heredada</span><span class="sxs-lookup"><span data-stu-id="b3419-126">How to: Hide an Inherited Variable</span></span>](how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="b3419-127">Shadows</span><span class="sxs-lookup"><span data-stu-id="b3419-127">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="b3419-128">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="b3419-128">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="b3419-129">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="b3419-129">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="b3419-130">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="b3419-130">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
