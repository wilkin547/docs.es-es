---
title: 'Cómo: Obtener acceso a una variable que oculta una clase derivada (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 8dd59dff5b8123331237db905432bbb4e94d62ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648052"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="7a039-102">Cómo: Obtener acceso a una variable que oculta una clase derivada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a039-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>
<span data-ttu-id="7a039-103">Cuando el código en una clase derivada tiene acceso a una variable, el compilador resuelve normalmente la referencia a la versión accesible más cercana, es decir, la versión accesible los mínimos pasos de derivación en sentido con versiones anteriores de la clase que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="7a039-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="7a039-104">Si la variable se define en la clase derivada, el código tiene acceso normalmente a esa definición.</span><span class="sxs-lookup"><span data-stu-id="7a039-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>  
  
 <span data-ttu-id="7a039-105">Si la variable de clase derivada oculta una variable en la clase base, oculta la versión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="7a039-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="7a039-106">Sin embargo, puede acceder a la variable de clase base mediante su calificación con la `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="7a039-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="7a039-107">Para obtener acceso a una variable de clase base oculta mediante una clase derivada</span><span class="sxs-lookup"><span data-stu-id="7a039-107">To access a base class variable hidden by a derived class</span></span>  
  
-   <span data-ttu-id="7a039-108">En una expresión o instrucción de asignación, incluya delante del nombre de variable con el `MyBase` palabra clave y un período (`.`).</span><span class="sxs-lookup"><span data-stu-id="7a039-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>  
  
     <span data-ttu-id="7a039-109">El compilador resuelve la referencia a la versión de la clase base de la variable.</span><span class="sxs-lookup"><span data-stu-id="7a039-109">The compiler resolves the reference to the base class version of the variable.</span></span>  
  
     <span data-ttu-id="7a039-110">En el ejemplo siguiente se ilustra el sombreado por herencia.</span><span class="sxs-lookup"><span data-stu-id="7a039-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="7a039-111">Realiza dos referencias, una que tiene acceso a la variable de sombreado y otra que omite el sombreado.</span><span class="sxs-lookup"><span data-stu-id="7a039-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="7a039-112">En el ejemplo anterior se declara la variable `shadowString` en la clase base y la sombra en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="7a039-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="7a039-113">El procedimiento `showStrings` en la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.</span><span class="sxs-lookup"><span data-stu-id="7a039-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="7a039-114">A continuación, muestra la versión sombreada cuando `shadowString` se califica con el `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="7a039-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7a039-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="7a039-115">Robust Programming</span></span>  
 <span data-ttu-id="7a039-116">Para reducir el riesgo de que hace referencia a una versión no deseada de una variable sombreada, puede calificar por completo todas las referencias a una variable sombreada.</span><span class="sxs-lookup"><span data-stu-id="7a039-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="7a039-117">El sombreado presenta más de una versión de una variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="7a039-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="7a039-118">Cuando una instrucción de código hace referencia al nombre de variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="7a039-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="7a039-119">Esto puede aumentar el riesgo de que hace referencia a una versión incorrecta de la variable.</span><span class="sxs-lookup"><span data-stu-id="7a039-119">This can increase the risk of referring to the wrong version of the variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a039-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a039-120">See Also</span></span>  
 [<span data-ttu-id="7a039-121">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="7a039-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="7a039-122">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a039-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="7a039-123">Diferencias entre sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="7a039-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="7a039-124">Ocultar una variable con el mismo nombre que su variable</span><span class="sxs-lookup"><span data-stu-id="7a039-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="7a039-125">Ocultar una variable heredada</span><span class="sxs-lookup"><span data-stu-id="7a039-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="7a039-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="7a039-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="7a039-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="7a039-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="7a039-128">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="7a039-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="7a039-129">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="7a039-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
