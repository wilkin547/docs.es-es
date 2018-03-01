---
title: "Definición de tipos anónimos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8b5b7eba55d719c1482b7224ecffc78b776feb00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="7d4df-102">Definición de tipos anónimos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d4df-102">Anonymous Type Definition (Visual Basic)</span></span>
<span data-ttu-id="7d4df-103">En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas para el tipo.</span><span class="sxs-lookup"><span data-stu-id="7d4df-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>  
  
## <a name="compiler-generated-code"></a><span data-ttu-id="7d4df-104">Código generado por el compilador</span><span class="sxs-lookup"><span data-stu-id="7d4df-104">Compiler-Generated Code</span></span>  
 <span data-ttu-id="7d4df-105">En la siguiente definición de `product`, el compilador crea una nueva definición de clase que contiene propiedades `Name`, `Price`, y `OnHand`.</span><span class="sxs-lookup"><span data-stu-id="7d4df-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 <span data-ttu-id="7d4df-106">La definición de clase contiene definiciones de propiedad similares al siguiente.</span><span class="sxs-lookup"><span data-stu-id="7d4df-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="7d4df-107">Tenga en cuenta que no hay ningún `Set` método para las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="7d4df-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="7d4df-108">Los valores de las propiedades de clave son de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="7d4df-108">The values of key properties are read-only.</span></span>  
  
```vb  
Public Class $Anonymous1  
    Private _name As String  
    Private _price As Double  
    Private _onHand As Integer  
     Public ReadOnly Property Name() As String  
        Get  
            Return _name  
        End Get  
    End Property  
  
    Public ReadOnly Property Price() As Double  
        Get  
            Return _price  
        End Get  
    End Property  
  
    Public Property OnHand() As Integer  
        Get  
            Return _onHand  
        End Get  
        Set(ByVal Value As Integer)  
            _onHand = Value  
        End Set  
    End Property  
  
End Class  
```  
  
 <span data-ttu-id="7d4df-109">Además, las definiciones de tipos anónimos contienen un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7d4df-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="7d4df-110">No se permiten constructores que requieren parámetros.</span><span class="sxs-lookup"><span data-stu-id="7d4df-110">Constructors that require parameters are not permitted.</span></span>  
  
 <span data-ttu-id="7d4df-111">Si una declaración de tipo anónimo contiene al menos una propiedad de clave, la definición de tipo invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, y <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d4df-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="7d4df-112">Si no se declara ninguna propiedad clave, solo <xref:System.Object.ToString%2A> se invalida.</span><span class="sxs-lookup"><span data-stu-id="7d4df-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="7d4df-113">Las invalidaciones proporcionan la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d4df-113">The overrides provide the following functionality:</span></span>  
  
-   <span data-ttu-id="7d4df-114">`Equals`Devuelve `True` si dos instancias de tipo anónimo son la misma instancia o si cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d4df-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>  
  
    -   <span data-ttu-id="7d4df-115">Tienen el mismo número de propiedades.</span><span class="sxs-lookup"><span data-stu-id="7d4df-115">They have the same number of properties.</span></span>  
  
    -   <span data-ttu-id="7d4df-116">Las propiedades se declaran en el mismo orden, con los mismos nombres y los mismos tipos deducidos.</span><span class="sxs-lookup"><span data-stu-id="7d4df-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="7d4df-117">Las comparaciones de nombres no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7d4df-117">Name comparisons are not case-sensitive.</span></span>  
  
    -   <span data-ttu-id="7d4df-118">Al menos una de las propiedades es una propiedad clave y el `Key` palabra clave se aplica a las mismas propiedades.</span><span class="sxs-lookup"><span data-stu-id="7d4df-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>  
  
    -   <span data-ttu-id="7d4df-119">Comparación de cada par correspondiente de propiedades de clave devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="7d4df-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>  
  
     <span data-ttu-id="7d4df-120">Por ejemplo, en los ejemplos siguientes, `Equals` devuelve `True` sólo para `employee01` y `employee08`.</span><span class="sxs-lookup"><span data-stu-id="7d4df-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="7d4df-121">El comentario que precede a cada línea especifica la razón por qué no coincide con la nueva instancia `employee01`.</span><span class="sxs-lookup"><span data-stu-id="7d4df-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   <span data-ttu-id="7d4df-122">`GetHashcode`Proporciona un algoritmo GetHashCode único correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d4df-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="7d4df-123">El algoritmo utiliza sólo las propiedades de clave para calcular el código hash.</span><span class="sxs-lookup"><span data-stu-id="7d4df-123">The algorithm uses only the key properties to compute the hash code.</span></span>  
  
-   <span data-ttu-id="7d4df-124">`ToString`Devuelve una cadena de valores de propiedad concatenados, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7d4df-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="7d4df-125">Clave y propiedades de clave no se incluyen.</span><span class="sxs-lookup"><span data-stu-id="7d4df-125">Both key and non-key properties are included.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 <span data-ttu-id="7d4df-126">Propiedades con nombre explícito de un tipo anónimo no se pueden entrar en conflicto con estos métodos generados.</span><span class="sxs-lookup"><span data-stu-id="7d4df-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="7d4df-127">Es decir, no puede usar `.Equals`, `.GetHashCode`, o `.ToString` a un nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7d4df-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="7d4df-128">Las definiciones de tipo anónimo que incluyen al menos una propiedad clave también implementan la <xref:System.IEquatable%601?displayProperty=nameWithType> interfaz, donde `T` es el tipo del tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="7d4df-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d4df-129">Declaraciones de tipos anónimos crear el mismo tipo anónimo sólo si se producen en el mismo ensamblado, sus propiedades tienen los mismos nombres y los mismos tipos deducidos, las propiedades se declaran en el mismo orden y se marcan las mismas propiedades como propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="7d4df-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4df-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d4df-130">See Also</span></span>  
 [<span data-ttu-id="7d4df-131">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="7d4df-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="7d4df-132">Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="7d4df-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
