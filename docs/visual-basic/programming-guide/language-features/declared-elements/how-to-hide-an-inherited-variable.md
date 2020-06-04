---
title: Procedimiento para ocultar una variable heredada
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
ms.openlocfilehash: f49bba0497f9f4f2774b01284c815bba9aaed119
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357275"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="bc77a-102">Cómo: Ocultar una variable heredada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc77a-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>

<span data-ttu-id="bc77a-103">Una clase derivada hereda todas las definiciones de su clase base.</span><span class="sxs-lookup"><span data-stu-id="bc77a-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="bc77a-104">Si desea definir una variable con el mismo nombre que un elemento de la clase base, puede ocultar, o *sombra*, ese elemento de clase base cuando defina la variable en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="bc77a-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="bc77a-105">Si lo hace, el código de la clase derivada accede a su variable a menos que omita explícitamente el mecanismo de sombreado.</span><span class="sxs-lookup"><span data-stu-id="bc77a-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>

<span data-ttu-id="bc77a-106">Otro motivo por el que podría querer ocultar una variable heredada es proteger contra la revisión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="bc77a-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="bc77a-107">La clase base puede someterse a un cambio que modifica el elemento que se va a heredar.</span><span class="sxs-lookup"><span data-stu-id="bc77a-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="bc77a-108">Si esto ocurre, el `Shadows` modificador fuerza las referencias de la clase derivada para que se resuelvan en la variable, en lugar de en el elemento de clase base.</span><span class="sxs-lookup"><span data-stu-id="bc77a-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>

## <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="bc77a-109">Para ocultar una variable heredada</span><span class="sxs-lookup"><span data-stu-id="bc77a-109">To hide an inherited variable</span></span>

1. <span data-ttu-id="bc77a-110">Asegúrese de que la variable que desea ocultar se declara en el nivel de clase (fuera de cualquier procedimiento).</span><span class="sxs-lookup"><span data-stu-id="bc77a-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="bc77a-111">De lo contrario, no es necesario ocultarlo.</span><span class="sxs-lookup"><span data-stu-id="bc77a-111">Otherwise, you do not need to hide it.</span></span>
  
2. <span data-ttu-id="bc77a-112">Dentro de la clase derivada, escriba una [instrucción Dim](../../../language-reference/statements/dim-statement.md) que declare la variable.</span><span class="sxs-lookup"><span data-stu-id="bc77a-112">Inside your derived class, write a [Dim Statement](../../../language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="bc77a-113">Use el mismo nombre que el de la variable heredada.</span><span class="sxs-lookup"><span data-stu-id="bc77a-113">Use the same name as that of the inherited variable.</span></span>

3. <span data-ttu-id="bc77a-114">Incluya la palabra clave [Shadows](../../../language-reference/modifiers/shadows.md) en la declaración.</span><span class="sxs-lookup"><span data-stu-id="bc77a-114">Include the [Shadows](../../../language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

     <span data-ttu-id="bc77a-115">Cuando el código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="bc77a-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

     <span data-ttu-id="bc77a-116">En el ejemplo siguiente se muestra la sombra de una variable heredada:</span><span class="sxs-lookup"><span data-stu-id="bc77a-116">The following example illustrates shadowing of an inherited variable:</span></span>
  
    ```vb  
    Public Class ShadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class ShadowDerivedClass  
        Inherits ShadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub ShowStrings()  
            Dim s As String = $"Unqualified shadowString: {shadowString}{vbCrLf}MyBase.shadowString: {MyBase.shadowString}"
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="bc77a-117">En el ejemplo anterior se declara la variable `shadowString` en la clase base y se sombrea en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="bc77a-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="bc77a-118">El procedimiento `ShowStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.</span><span class="sxs-lookup"><span data-stu-id="bc77a-118">The procedure `ShowStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="bc77a-119">A continuación, muestra la versión sombreada cuando `shadowString` se califica con la `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="bc77a-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bc77a-120">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="bc77a-120">Robust programming</span></span>

<span data-ttu-id="bc77a-121">La sombra introduce más de una versión de una variable con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="bc77a-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="bc77a-122">Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="bc77a-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="bc77a-123">Esto puede aumentar el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra.</span><span class="sxs-lookup"><span data-stu-id="bc77a-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="bc77a-124">Puede reducir este riesgo calificando por completo todas las referencias a una variable de la que se ha realizado una copia sombra.</span><span class="sxs-lookup"><span data-stu-id="bc77a-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc77a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc77a-125">See also</span></span>

- [<span data-ttu-id="bc77a-126">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="bc77a-126">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="bc77a-127">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc77a-127">Shadowing in Visual Basic</span></span>](shadowing.md)
- [<span data-ttu-id="bc77a-128">Diferencias entre sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="bc77a-128">Differences Between Shadowing and Overriding</span></span>](differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="bc77a-129">Procedimiento para ocultar una variable con el mismo nombre que su variable</span><span class="sxs-lookup"><span data-stu-id="bc77a-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="bc77a-130">Procedimiento para obtener acceso a una variable que se encuentra oculta por una clase derivada</span><span class="sxs-lookup"><span data-stu-id="bc77a-130">How to: Access a Variable Hidden by a Derived Class</span></span>](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="bc77a-131">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="bc77a-131">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="bc77a-132">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="bc77a-132">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="bc77a-133">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="bc77a-133">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
