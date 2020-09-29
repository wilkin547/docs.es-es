---
title: 'Constructores estáticos: Guía de programación de C#'
description: Un constructor estático de C# inicializa datos estáticos o realiza una acción ejecutada una sola vez antes de que se cree la primera instancia o se haga referencia a los miembros estáticos.
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 07b3e54c9ffeb1abacaf5ddd04d2058697e653e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203974"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="27b8c-103">Constructores estáticos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="27b8c-103">Static Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="27b8c-104">Un constructor estático se usa para inicializar cualquier dato [estático](../../language-reference/keywords/static.md) o realizar una acción determinada que solo debe realizarse una vez.</span><span class="sxs-lookup"><span data-stu-id="27b8c-104">A static constructor is used to initialize any [static](../../language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="27b8c-105">Es llamado automáticamente antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.</span><span class="sxs-lookup"><span data-stu-id="27b8c-105">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  

## <a name="remarks"></a><span data-ttu-id="27b8c-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27b8c-106">Remarks</span></span>

<span data-ttu-id="27b8c-107">Los constructores estáticos tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="27b8c-107">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="27b8c-108">Un constructor estático no permite modificadores de acceso ni tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="27b8c-108">A static constructor does not take access modifiers or have parameters.</span></span>  

- <span data-ttu-id="27b8c-109">Una clase o struct solo puede tener un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="27b8c-109">A class or struct can only have one static constructor.</span></span>

- <span data-ttu-id="27b8c-110">Los constructores estáticos no se pueden heredar ni sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="27b8c-110">Static constructors cannot be inherited or overloaded.</span></span>

- <span data-ttu-id="27b8c-111">No se puede llamar a un constructor estático directamente y solo está pensado para que Common Language Runtime (CLR) lo llame.</span><span class="sxs-lookup"><span data-stu-id="27b8c-111">A static constructor cannot be called directly and is only meant to be called by the common language runtime (CLR).</span></span> <span data-ttu-id="27b8c-112">Se invoca automáticamente.</span><span class="sxs-lookup"><span data-stu-id="27b8c-112">It is invoked automatically.</span></span>

- <span data-ttu-id="27b8c-113">El usuario no puede controlar cuándo se ejecuta el constructor estático en el programa.</span><span class="sxs-lookup"><span data-stu-id="27b8c-113">The user has no control on when the static constructor is executed in the program.</span></span>
  
- <span data-ttu-id="27b8c-114">Se le llama automáticamente para inicializar la [clase](../../language-reference/keywords/class.md) antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.</span><span class="sxs-lookup"><span data-stu-id="27b8c-114">A static constructor is called automatically to initialize the [class](../../language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span> <span data-ttu-id="27b8c-115">Un constructor estático se ejecutará antes que un constructor de instancia.</span><span class="sxs-lookup"><span data-stu-id="27b8c-115">A static constructor will run before an instance constructor.</span></span> <span data-ttu-id="27b8c-116">Se llama al constructor estático de un tipo cuando se invoca un método estático asignado a un evento o un delegado y no cuando este se asigna.</span><span class="sxs-lookup"><span data-stu-id="27b8c-116">A type's static constructor is called when a static method assigned to an event or a delegate is invoked and not when it is assigned.</span></span> <span data-ttu-id="27b8c-117">Si los inicializadores de variable del campo estático están presentes en la clase o el constructor estático, se ejecutarán en el orden textual en el que aparecen en la declaración de clase inmediatamente anterior a la ejecución del constructor estático.</span><span class="sxs-lookup"><span data-stu-id="27b8c-117">If static field variable initializers are present in the class of the static constructor, they will be executed in the textual order in which they appear in the class declaration immediately prior to the execution of the static constructor.</span></span>

- <span data-ttu-id="27b8c-118">Si no proporciona un constructor estático para inicializar los campos estáticos, todos los campos estáticos se inicializan en su valor predeterminado como se muestra en [Valores predeterminados de los tipos de C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="27b8c-118">If you don't provide a static constructor to initialize static fields, all static fields are initialized to their default value as listed in [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span>
  
- <span data-ttu-id="27b8c-119">Si un constructor estático inicia una excepción, el motor en tiempo de ejecución no lo invocará una segunda vez y el tipo seguirá sin inicializar durante el período de duración del dominio de aplicación donde se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="27b8c-119">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span> <span data-ttu-id="27b8c-120">Normalmente, se inicia una excepción <xref:System.TypeInitializationException> cuando un constructor estático no puede crear una instancia de un tipo o para una excepción no controlada que se produce dentro de un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="27b8c-120">Most commonly, a <xref:System.TypeInitializationException> exception is thrown when a static constructor is unable to instantiate a type or for an unhandled exception occurring within a static constructor.</span></span> <span data-ttu-id="27b8c-121">En el caso de los constructores estáticos implícitos no definidos de forma explícita en el código fuente, la solución de problemas puede requerir la inspección del código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="27b8c-121">For implicit static constructors that are not explicitly defined in source code, troubleshooting may require inspection of the intermediate language (IL) code.</span></span>

- <span data-ttu-id="27b8c-122">La presencia de un constructor estático evita la adición del atributo de tipo <xref:System.Reflection.TypeAttributes.BeforeFieldInit>.</span><span class="sxs-lookup"><span data-stu-id="27b8c-122">The presence of a static constructor prevents the addition of the <xref:System.Reflection.TypeAttributes.BeforeFieldInit> type attribute.</span></span> <span data-ttu-id="27b8c-123">Esto limita la optimización en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="27b8c-123">This limits runtime optimization.</span></span>

- <span data-ttu-id="27b8c-124">Un campo declarado como `static readonly` solo se puede asignar como parte de su declaración o en un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="27b8c-124">A field declared as `static readonly` may only be assigned as part of its declaration or in a static constructor.</span></span> <span data-ttu-id="27b8c-125">Si no se necesita un constructor estático explícito, inicialice campos estáticos en la declaración, en lugar de a través de un constructor estático para una mejor optimización en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="27b8c-125">When an explicit static constructor is not required, initialize static fields at declaration, rather than through a static constructor for better runtime optimization.</span></span>

> [!Note]
> <span data-ttu-id="27b8c-126">Aunque no es directamente accesible, la presencia de un constructor estático explícito debe documentarse para ayudar con la solución de problemas de excepciones de inicialización.</span><span class="sxs-lookup"><span data-stu-id="27b8c-126">Though not directly accessible, the presence of an explicit static constructor should be documented to assist with troubleshooting initialization exceptions.</span></span>

### <a name="usage"></a><span data-ttu-id="27b8c-127">Uso</span><span class="sxs-lookup"><span data-stu-id="27b8c-127">Usage</span></span>

- <span data-ttu-id="27b8c-128">Los constructores estáticos se usan normalmente cuando la clase hace uso de un archivo de registro y el constructor escribe entradas en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="27b8c-128">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
- <span data-ttu-id="27b8c-129">Los constructores estáticos también son útiles al crear clases contenedoras para código no administrado, cuando el constructor puede llamar al método `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="27b8c-129">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  

- <span data-ttu-id="27b8c-130">Los constructores estáticos también son un lugar adecuado para aplicar comprobaciones en tiempo de ejecución en el parámetro de tipo que no se puede comprobar en tiempo de compilación a través de restricciones (restricciones de parámetro de tipo).</span><span class="sxs-lookup"><span data-stu-id="27b8c-130">Static constructors are also a convenient place to enforce run-time checks on the type parameter that cannot be checked at compile time via constraints (Type parameter constraints).</span></span>

## <a name="example"></a><span data-ttu-id="27b8c-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27b8c-131">Example</span></span>

 <span data-ttu-id="27b8c-132">En este ejemplo, la clase `Bus` tiene un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="27b8c-132">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="27b8c-133">Cuando se crea la primera instancia de `Bus` (`bus1`), se invoca el constructor estático para inicializar la clase.</span><span class="sxs-lookup"><span data-stu-id="27b8c-133">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="27b8c-134">En el resultado del ejemplo, se comprueba que el constructor estático se ejecuta solo una vez, incluso si se crean dos instancias de `Bus`, y que se ejecuta antes de que se ejecute el constructor de instancia.</span><span class="sxs-lookup"><span data-stu-id="27b8c-134">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="27b8c-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="27b8c-135">C# language specification</span></span>

<span data-ttu-id="27b8c-136">Para obtener más información, consulte la sección sobre [constructores estáticos](~/_csharplang/spec/classes.md#static-constructors) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="27b8c-136">For more information, see the [Static constructors](~/_csharplang/spec/classes.md#static-constructors) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="27b8c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="27b8c-137">See also</span></span>

- [<span data-ttu-id="27b8c-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="27b8c-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="27b8c-139">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="27b8c-139">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="27b8c-140">Constructores</span><span class="sxs-lookup"><span data-stu-id="27b8c-140">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="27b8c-141">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="27b8c-141">Static Classes and Static Class Members</span></span>](./static-classes-and-static-class-members.md)
- [<span data-ttu-id="27b8c-142">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="27b8c-142">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="27b8c-143">Instrucciones de diseño de constructores</span><span class="sxs-lookup"><span data-stu-id="27b8c-143">Constructor Design Guidelines</span></span>](../../../standard/design-guidelines/constructor.md#type-constructor-guidelines)
- [<span data-ttu-id="27b8c-144">Advertencia de seguridad - CA2121: Los constructores estáticos deben ser privados</span><span class="sxs-lookup"><span data-stu-id="27b8c-144">Security Warning - CA2121: Static constructors should be private</span></span>](/visualstudio/code-quality/ca2121-static-constructors-should-be-private)
