---
title: "Constructores privados (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1ccd3db5f95e3a237bb37d9e09c34f415fcfd752
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="10e79-102">Constructores privados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="10e79-102">Private Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="10e79-103">Un constructor privado es un constructor de instancia especial.</span><span class="sxs-lookup"><span data-stu-id="10e79-103">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="10e79-104">Se usa generalmente en clases que contienen solo miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="10e79-104">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="10e79-105">Si una clase tiene uno o más constructores privados y ningún constructor público, el resto de clases (excepto las anidadas) no podrán crear instancias de esta clase.</span><span class="sxs-lookup"><span data-stu-id="10e79-105">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="10e79-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="10e79-106">For example:</span></span>  
  
 <span data-ttu-id="10e79-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="10e79-107">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="10e79-108">La declaración de un constructor vacío evita la generación automática de un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10e79-108">The declaration of the empty constructor prevents the automatic generation of a default constructor.</span></span> <span data-ttu-id="10e79-109">Observe que si no usa un modificador de acceso en el constructor, este será privado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="10e79-109">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="10e79-110">En cambio, normalmente se usa el modificador [private](../../../csharp/language-reference/keywords/private.md) de manera explícita para aclarar que no es posible crear una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="10e79-110">However, the [private](../../../csharp/language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="10e79-111">Los constructores privados se usan para evitar la creación de instancias de una clase cuando no hay campos o métodos de instancia, por ejemplo, la clase <xref:System.Math>, o cuando se llama a un método para obtener una instancia de una clase.</span><span class="sxs-lookup"><span data-stu-id="10e79-111">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="10e79-112">Si todos los métodos de la clase son estáticos, considere convertir la clase completa en estática.</span><span class="sxs-lookup"><span data-stu-id="10e79-112">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="10e79-113">Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="10e79-113">For more information see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10e79-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10e79-114">Example</span></span>  
 <span data-ttu-id="10e79-115">El siguiente es un ejemplo de clase que usa un constructor privado.</span><span class="sxs-lookup"><span data-stu-id="10e79-115">The following is an example of a class using a private constructor.</span></span>  
  
 <span data-ttu-id="10e79-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="10e79-116">[!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="10e79-117">Observe que si quita el comentario de la siguiente instrucción del ejemplo, se producirá un error porque el constructor es inaccesible debido a su nivel de protección:</span><span class="sxs-lookup"><span data-stu-id="10e79-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 <span data-ttu-id="10e79-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="10e79-118">[!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="10e79-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="10e79-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10e79-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="10e79-120">See Also</span></span>  
 <span data-ttu-id="10e79-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="10e79-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="10e79-122">[Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="10e79-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="10e79-123">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md)  (Constructores [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="10e79-123">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="10e79-124">[Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="10e79-124">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="10e79-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="10e79-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 [<span data-ttu-id="10e79-126">public</span><span class="sxs-lookup"><span data-stu-id="10e79-126">public</span></span>](../../../csharp/language-reference/keywords/public.md)

