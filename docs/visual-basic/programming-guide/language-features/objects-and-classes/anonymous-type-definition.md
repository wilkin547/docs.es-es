---
title: Definición de tipos anónimos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: e74b4c7298a80f724031cc4ac1feb49ebae8f7cb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975620"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="dd3a9-102">Definición de tipos anónimos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd3a9-102">Anonymous Type Definition (Visual Basic)</span></span>
<span data-ttu-id="dd3a9-103">En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades para el tipo especificadas.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>  
  
## <a name="compiler-generated-code"></a><span data-ttu-id="dd3a9-104">Código generado por el compilador</span><span class="sxs-lookup"><span data-stu-id="dd3a9-104">Compiler-Generated Code</span></span>  
 <span data-ttu-id="dd3a9-105">La siguiente definición de `product`, el compilador crea una nueva definición de clase que contiene propiedades `Name`, `Price`, y `OnHand`.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]  
  
 <span data-ttu-id="dd3a9-106">La definición de clase contiene las definiciones de propiedad similares al siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="dd3a9-107">Tenga en cuenta que no hay ningún `Set` método para las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="dd3a9-108">Los valores de las propiedades clave son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-108">The values of key properties are read-only.</span></span>  
  
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
  
 <span data-ttu-id="dd3a9-109">Además, las definiciones de tipo anónimo contienen un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="dd3a9-110">No se permiten los constructores que requieren parámetros.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-110">Constructors that require parameters are not permitted.</span></span>  
  
 <span data-ttu-id="dd3a9-111">Si una declaración de tipo anónimo contiene al menos una propiedad clave, la definición de tipo invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, y <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="dd3a9-112">Si no se declara ninguna propiedad clave, solo <xref:System.Object.ToString%2A> se reemplaza.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="dd3a9-113">Las invalidaciones proporcionan la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd3a9-113">The overrides provide the following functionality:</span></span>  
  
-   <span data-ttu-id="dd3a9-114">`Equals` Devuelve `True` si dos instancias de tipo anónimo son la misma instancia o si cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd3a9-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>  
  
    -   <span data-ttu-id="dd3a9-115">Tienen el mismo número de propiedades.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-115">They have the same number of properties.</span></span>  
  
    -   <span data-ttu-id="dd3a9-116">Las propiedades se declaran en el mismo orden, con los mismos nombres y los mismos tipos deducidos.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="dd3a9-117">Las comparaciones de nombres no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-117">Name comparisons are not case-sensitive.</span></span>  
  
    -   <span data-ttu-id="dd3a9-118">Al menos una de las propiedades es una propiedad clave y el `Key` palabra clave se aplica a las mismas propiedades.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>  
  
    -   <span data-ttu-id="dd3a9-119">Comparación de cada par correspondiente de las propiedades de clave devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>  
  
     <span data-ttu-id="dd3a9-120">Por ejemplo, en los ejemplos siguientes, `Equals` devuelve `True` sólo para `employee01` y `employee08`.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="dd3a9-121">El comentario antes de cada línea especifica la razón por la nueva instancia no coinciden `employee01`.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]  
  
-   <span data-ttu-id="dd3a9-122">`GetHashcode` Proporciona un algoritmo GetHashCode único correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="dd3a9-123">El algoritmo usa sólo las propiedades de clave para calcular el código hash.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-123">The algorithm uses only the key properties to compute the hash code.</span></span>  
  
-   <span data-ttu-id="dd3a9-124">`ToString` Devuelve una cadena concatenada de valores de propiedad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="dd3a9-125">Clave y propiedades de clave no se incluyen.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-125">Both key and non-key properties are included.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]  
  
 <span data-ttu-id="dd3a9-126">Propiedades con nombre explícito de un tipo anónimo no pueden entrar en conflicto con estos métodos generados.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="dd3a9-127">Es decir, no puede usar `.Equals`, `.GetHashCode`, o `.ToString` a una propiedad de nombre.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="dd3a9-128">Las definiciones de tipo anónimo que incluyen al menos una propiedad de clave también implementan la <xref:System.IEquatable%601?displayProperty=nameWithType> interfaz, donde `T` es el tipo del tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd3a9-129">Declaraciones de tipos anónimos creación el mismo tipo anónimo sólo si se producen en el mismo ensamblado, sus propiedades tienen los mismos nombres y los mismos tipos deducidos, las propiedades se declaran en el mismo orden y las mismas propiedades se marcan como propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="dd3a9-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3a9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd3a9-130">See also</span></span>
- [<span data-ttu-id="dd3a9-131">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="dd3a9-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="dd3a9-132">Cómo: Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="dd3a9-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
