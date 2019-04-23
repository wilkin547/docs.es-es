---
title: Procedimiento Ocultar una Variable heredada (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: ee147ecd00b88b538ace32844c42ac9c5022b2ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331707"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="ba900-102">Procedimiento Ocultar una Variable heredada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba900-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="ba900-103">Una clase derivada hereda todas las definiciones de su clase base.</span><span class="sxs-lookup"><span data-stu-id="ba900-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="ba900-104">Si desea definir una variable con el mismo nombre que un elemento de la clase base, puede ocultar, o *sombra*, ese elemento de la clase base al definir la variable en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ba900-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="ba900-105">Si lo hace, el código en la clase derivada tiene acceso a la variable a menos que explícitamente omite el mecanismo de sombreado.</span><span class="sxs-lookup"><span data-stu-id="ba900-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="ba900-106">Es otro motivo que desea ocultar una variable heredada para protegerse frente a la revisión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="ba900-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="ba900-107">La clase base puede sufrir un cambio que modifica el elemento que se hereda.</span><span class="sxs-lookup"><span data-stu-id="ba900-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="ba900-108">Si esto ocurre, el `Shadows` modificador fuerza las referencias de la clase derivada que se resuelva a la variable, en lugar de en el elemento de la clase base.</span><span class="sxs-lookup"><span data-stu-id="ba900-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="ba900-109">Para ocultar una variable heredada</span><span class="sxs-lookup"><span data-stu-id="ba900-109">To hide an inherited variable</span></span>  
  
1. <span data-ttu-id="ba900-110">Asegúrese de que se declara la variable que desea ocultar en el nivel de clase (fuera de cualquier procedimiento).</span><span class="sxs-lookup"><span data-stu-id="ba900-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="ba900-111">En caso contrario, no es necesario ocultarlo.</span><span class="sxs-lookup"><span data-stu-id="ba900-111">Otherwise you do not need to hide it.</span></span>  
  
2. <span data-ttu-id="ba900-112">Dentro de la clase derivada, escribe un [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) declarar la variable.</span><span class="sxs-lookup"><span data-stu-id="ba900-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="ba900-113">Use el mismo nombre que el de la variable heredada.</span><span class="sxs-lookup"><span data-stu-id="ba900-113">Use the same name as that of the inherited variable.</span></span>  
  
3. <span data-ttu-id="ba900-114">Incluir el [sombras](../../../../visual-basic/language-reference/modifiers/shadows.md) palabra clave en la declaración.</span><span class="sxs-lookup"><span data-stu-id="ba900-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="ba900-115">Cuando el código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="ba900-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="ba900-116">El ejemplo siguiente ilustra el sombreado de una variable heredada.</span><span class="sxs-lookup"><span data-stu-id="ba900-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
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
  
     <span data-ttu-id="ba900-117">El ejemplo anterior declara la variable `shadowString` en la clase base y lo reemplaza en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ba900-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="ba900-118">El procedimiento `showStrings` en la clase derivada, muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.</span><span class="sxs-lookup"><span data-stu-id="ba900-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="ba900-119">A continuación, muestra la versión sombreada cuando `shadowString` se califica con el `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ba900-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ba900-120">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ba900-120">Robust Programming</span></span>  
 <span data-ttu-id="ba900-121">El sombreado presenta más de una versión de una variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="ba900-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="ba900-122">Cuando una instrucción de código hace referencia al nombre de variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="ba900-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="ba900-123">Esto puede aumentar el riesgo de que hace referencia a una versión no deseada de una variable sombreada.</span><span class="sxs-lookup"><span data-stu-id="ba900-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="ba900-124">Puede reducir este riesgo si califica completamente todas las referencias a una variable sombreada.</span><span class="sxs-lookup"><span data-stu-id="ba900-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba900-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba900-125">See also</span></span>

- [<span data-ttu-id="ba900-126">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="ba900-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="ba900-127">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba900-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="ba900-128">Diferencias entre sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="ba900-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="ba900-129">Cómo: Ocultar una Variable con el mismo nombre que su Variable</span><span class="sxs-lookup"><span data-stu-id="ba900-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="ba900-130">Cómo: Obtener acceso a una Variable que oculta una clase derivada</span><span class="sxs-lookup"><span data-stu-id="ba900-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="ba900-131">Overrides</span><span class="sxs-lookup"><span data-stu-id="ba900-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="ba900-132">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="ba900-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="ba900-133">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="ba900-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
