---
title: 'Constructores estáticos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 74932c9a080a077a60ecbc45c997108afa176956
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676892"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="9cc3f-102">Constructores estáticos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9cc3f-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="9cc3f-103">Un constructor estático se usa para inicializar cualquier dato [estático](../../../csharp/language-reference/keywords/static.md) o realizar una acción determinada que solo debe realizarse una vez.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="9cc3f-104">Es llamado automáticamente antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 <span data-ttu-id="9cc3f-105">Los constructores estáticos tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9cc3f-105">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="9cc3f-106">Un constructor estático no permite modificadores de acceso ni tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="9cc3f-107">Se le llama automáticamente para inicializar la [clase](../../../csharp/language-reference/keywords/class.md) antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="9cc3f-108">Un constructor estático no puede ser llamado directamente.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-108">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="9cc3f-109">El usuario no puede controlar cuándo se ejecuta el constructor estático en el programa.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-109">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="9cc3f-110">Los constructores estáticos se usan normalmente cuando la clase hace uso de un archivo de registro y el constructor escribe entradas en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-110">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="9cc3f-111">Los constructores estáticos también son útiles al crear clases contenedoras para código no administrado, cuando el constructor puede llamar al método `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-111">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="9cc3f-112">Si un constructor estático inicia una excepción, el motor en tiempo de ejecución no lo invocará una segunda vez y el tipo seguirá sin inicializar durante el período de duración del dominio de aplicación donde se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-112">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cc3f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cc3f-113">Example</span></span>  
 <span data-ttu-id="9cc3f-114">En este ejemplo, la clase `Bus` tiene un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-114">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="9cc3f-115">Cuando se crea la primera instancia de `Bus` (`bus1`), se invoca el constructor estático para inicializar la clase.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-115">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="9cc3f-116">En el resultado del ejemplo, se comprueba que el constructor estático se ejecuta solo una vez, incluso si se crean dos instancias de `Bus`, y que se ejecuta antes de que se ejecute el constructor de instancia.</span><span class="sxs-lookup"><span data-stu-id="9cc3f-116">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9cc3f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cc3f-117">See also</span></span>

- [<span data-ttu-id="9cc3f-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9cc3f-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9cc3f-119">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="9cc3f-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="9cc3f-120">Constructores</span><span class="sxs-lookup"><span data-stu-id="9cc3f-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="9cc3f-121">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="9cc3f-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="9cc3f-122">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="9cc3f-122">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
