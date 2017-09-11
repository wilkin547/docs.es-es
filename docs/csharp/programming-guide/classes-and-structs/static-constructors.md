---
title: "Constructores estáticos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
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
ms.openlocfilehash: 73df76c61f393bf5fe09af66935acfbac4b5663f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="5ab57-102">Constructores estáticos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5ab57-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="5ab57-103">Un constructor estático se usa para inicializar cualquier dato [estático](../../../csharp/language-reference/keywords/static.md) o realizar una acción determinada que solo debe realizarse una vez.</span><span class="sxs-lookup"><span data-stu-id="5ab57-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="5ab57-104">Es llamado automáticamente antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.</span><span class="sxs-lookup"><span data-stu-id="5ab57-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 <span data-ttu-id="5ab57-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5ab57-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="5ab57-106">Los constructores estáticos tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="5ab57-106">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="5ab57-107">Un constructor estático no permite modificadores de acceso ni tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="5ab57-107">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="5ab57-108">Se le llama automáticamente para inicializar la [clase](../../../csharp/language-reference/keywords/class.md) antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.</span><span class="sxs-lookup"><span data-stu-id="5ab57-108">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="5ab57-109">Un constructor estático no puede ser llamado directamente.</span><span class="sxs-lookup"><span data-stu-id="5ab57-109">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="5ab57-110">El usuario no puede controlar cuándo se ejecuta el constructor estático en el programa.</span><span class="sxs-lookup"><span data-stu-id="5ab57-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="5ab57-111">Los constructores estáticos se usan normalmente cuando la clase hace uso de un archivo de registro y el constructor escribe entradas en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="5ab57-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="5ab57-112">Los constructores estáticos también son útiles al crear clases contenedoras para código no administrado, cuando el constructor puede llamar al método `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="5ab57-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="5ab57-113">Si un constructor estático inicia una excepción, el motor en tiempo de ejecución no lo invocará una segunda vez y el tipo seguirá sin inicializar durante el período de duración del dominio de aplicación donde se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="5ab57-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ab57-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ab57-114">Example</span></span>  
 <span data-ttu-id="5ab57-115">En este ejemplo, la clase `Bus` tiene un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="5ab57-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="5ab57-116">Cuando se crea la primera instancia de `Bus` (`bus1`), se invoca el constructor estático para inicializar la clase.</span><span class="sxs-lookup"><span data-stu-id="5ab57-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="5ab57-117">En el resultado del ejemplo, se comprueba que el constructor estático se ejecuta solo una vez, incluso si se crean dos instancias de `Bus`, y que se ejecuta antes de que se ejecute el constructor de instancia.</span><span class="sxs-lookup"><span data-stu-id="5ab57-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 <span data-ttu-id="5ab57-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5ab57-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab57-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ab57-119">See Also</span></span>  
 <span data-ttu-id="5ab57-120">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ab57-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5ab57-121">[Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="5ab57-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="5ab57-122">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md)  (Constructores [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="5ab57-122">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="5ab57-123">[Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="5ab57-123">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 [<span data-ttu-id="5ab57-124">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="5ab57-124">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

