---
title: "Constructores privados (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 79660cd4545fff43ac3dd6ab797fd20c0f882e05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="86e84-102">Constructores privados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="86e84-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="86e84-103">Un constructor privado es un constructor de instancia especial.</span><span class="sxs-lookup"><span data-stu-id="86e84-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="86e84-104">Se usa generalmente en clases que contienen solo miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="86e84-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="86e84-105">Si una clase tiene uno o más constructores privados y ningún constructor público, el resto de clases (excepto las anidadas) no podrán crear instancias de esta clase.</span><span class="sxs-lookup"><span data-stu-id="86e84-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="86e84-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86e84-106">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 <span data-ttu-id="86e84-107">La declaración de un constructor vacío evita la generación automática de un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="86e84-107">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="86e84-108">Observe que si no usa un modificador de acceso en el constructor, este será privado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="86e84-108">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="86e84-109">En cambio, normalmente se usa el modificador [private](../../../csharp/language-reference/keywords/private.md) de manera explícita para aclarar que no es posible crear una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="86e84-109">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="86e84-110">Los constructores privados se usan para evitar la creación de instancias de una clase cuando no hay campos o métodos de instancia, por ejemplo, la clase <xref:System.Math>, o cuando se llama a un método para obtener una instancia de una clase.</span><span class="sxs-lookup"><span data-stu-id="86e84-110">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="86e84-111">Si todos los métodos de la clase son estáticos, considere convertir la clase completa en estática.</span><span class="sxs-lookup"><span data-stu-id="86e84-111">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="86e84-112">Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="86e84-112">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="86e84-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86e84-113">Example</span></span>  
 <span data-ttu-id="86e84-114">El siguiente es un ejemplo de clase que usa un constructor privado.</span><span class="sxs-lookup"><span data-stu-id="86e84-114">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 <span data-ttu-id="86e84-115">Observe que si quita el comentario de la siguiente instrucción del ejemplo, se producirá un error porque el constructor es inaccesible debido a su nivel de protección:</span><span class="sxs-lookup"><span data-stu-id="86e84-115">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="86e84-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="86e84-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86e84-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="86e84-117">See Also</span></span>  
 [<span data-ttu-id="86e84-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="86e84-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="86e84-119">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="86e84-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="86e84-120">Constructores</span><span class="sxs-lookup"><span data-stu-id="86e84-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="86e84-121">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="86e84-121">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [<span data-ttu-id="86e84-122">private</span><span class="sxs-lookup"><span data-stu-id="86e84-122">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="86e84-123">public</span><span class="sxs-lookup"><span data-stu-id="86e84-123">public</span></span>](../../../csharp/language-reference/keywords/public.md)
