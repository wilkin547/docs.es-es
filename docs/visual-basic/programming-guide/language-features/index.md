---
title: Características del lenguaje Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, elements of
- Visual Basic code
ms.assetid: b0b21730-298c-47e6-9a2f-cc81f628067b
ms.openlocfilehash: a8f6da4dc42244fbadbaf0e96b0dd281a3f7ccb2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43659712"
---
# <a name="visual-basic-language-features"></a><span data-ttu-id="1f630-102">Características del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f630-102">Visual Basic Language Features</span></span>
<span data-ttu-id="1f630-103">Los temas siguientes se presentan y tratan los componentes esenciales de Visual Basic, un lenguaje de programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="1f630-103">The following topics introduce and discuss the essential components of Visual Basic, an object-oriented programming language.</span></span> <span data-ttu-id="1f630-104">Después de crear la interfaz de usuario para su aplicación con formularios y controles, debe escribir el código que define el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f630-104">After creating the user interface for your application using forms and controls, you need to write the code that defines the application's behavior.</span></span> <span data-ttu-id="1f630-105">Al igual que con cualquier lenguaje de programación modernos, Visual Basic admite un número de elementos de lenguaje y construcciones de programación comunes.</span><span class="sxs-lookup"><span data-stu-id="1f630-105">As with any modern programming language, Visual Basic supports a number of common programming constructs and language elements.</span></span>  
  
 <span data-ttu-id="1f630-106">Si ha programado en otros lenguajes, gran parte del material tratado en esta sección le resultará familiar.</span><span class="sxs-lookup"><span data-stu-id="1f630-106">If you have programmed in other languages, much of the material covered in this section might seem familiar.</span></span> <span data-ttu-id="1f630-107">Aunque la mayoría de las construcciones son similar a los de otros lenguajes, la naturaleza orientada a eventos de Visual Basic presenta algunas diferencias sutiles.</span><span class="sxs-lookup"><span data-stu-id="1f630-107">While most of the constructs are similar to those in other languages, the event-driven nature of Visual Basic introduces some subtle differences.</span></span>  
  
 <span data-ttu-id="1f630-108">Si está familiarizado con la programación, el material de esta sección sirve como introducción a los bloques de creación básicos para escribir código.</span><span class="sxs-lookup"><span data-stu-id="1f630-108">If you are new to programming, the material in this section serves as an introduction to the basic building blocks for writing code.</span></span> <span data-ttu-id="1f630-109">Una vez que comprenda los conceptos básicos, puede crear aplicaciones eficaces con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f630-109">Once you understand the basics, you can create powerful applications using Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f630-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1f630-110">In This Section</span></span>  
 [<span data-ttu-id="1f630-111">Matrices</span><span class="sxs-lookup"><span data-stu-id="1f630-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="1f630-112">Explica cómo hacer el código más compacto y eficaz mediante la declaración y utilización de matrices, que contienen varios valores relacionados.</span><span class="sxs-lookup"><span data-stu-id="1f630-112">Discusses making your code more compact and powerful by declaring and using arrays, which hold multiple related values.</span></span>  
  
 [<span data-ttu-id="1f630-113">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="1f630-113">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 <span data-ttu-id="1f630-114">Describe los inicializadores de colección, que permiten crear una colección y rellenarla con un conjunto inicial de valores.</span><span class="sxs-lookup"><span data-stu-id="1f630-114">Describes collection initializers, which enable you to create a collection and populate it with an initial set of values.</span></span>  
  
 [<span data-ttu-id="1f630-115">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="1f630-115">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 <span data-ttu-id="1f630-116">Explica el almacenamiento de valores inmutables para su uso repetido, incluidos los conjuntos de valores de constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="1f630-116">Discusses storing unchanging values for repeated use, including sets of related constant values.</span></span>  
  
 [<span data-ttu-id="1f630-117">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="1f630-117">Control Flow</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 <span data-ttu-id="1f630-118">Muestra cómo regular el flujo de la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="1f630-118">Shows how to regulate the flow of your program's execution.</span></span>  
  
 [<span data-ttu-id="1f630-119">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="1f630-119">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="1f630-120">Describe qué tipos de datos puede contener un elemento de programación y cómo almacenarlos.</span><span class="sxs-lookup"><span data-stu-id="1f630-120">Describes what kinds of data a programming element can hold and how that data is stored.</span></span>  
  
 [<span data-ttu-id="1f630-121">Elementos declarados</span><span class="sxs-lookup"><span data-stu-id="1f630-121">Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 <span data-ttu-id="1f630-122">Abarca la programación de elementos que puede declarar, sus nombres y características, y cómo el compilador resuelve las referencias a ellos.</span><span class="sxs-lookup"><span data-stu-id="1f630-122">Covers programming elements you can declare, their names and characteristics, and how the compiler resolves references to them.</span></span>  
  
 [<span data-ttu-id="1f630-123">Delegados</span><span class="sxs-lookup"><span data-stu-id="1f630-123">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 <span data-ttu-id="1f630-124">Se proporciona una introducción a los delegados y se explica cómo se usan en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f630-124">Provides an introduction to delegates and how they are used in Visual Basic.</span></span>  
  
 [<span data-ttu-id="1f630-125">Enlace en tiempo de compilación y en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1f630-125">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 <span data-ttu-id="1f630-126">Describe los enlaces, que realiza el compilador cuando se asigna un objeto a una variable de objeto, y las diferencias entre los objetos con enlace anticipado y con enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1f630-126">Describes binding, which is performed by the compiler when an object is assigned to an object variable, and the differences between early-bound and late-bound objects.</span></span>  
  
 [<span data-ttu-id="1f630-127">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="1f630-127">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 <span data-ttu-id="1f630-128">Proporciona información general sobre los errores de sintaxis, errores en tiempo de ejecución y errores lógicos.</span><span class="sxs-lookup"><span data-stu-id="1f630-128">Provides an overview of syntax errors, run-time errors, and logic errors.</span></span>  
  
 [<span data-ttu-id="1f630-129">Eventos</span><span class="sxs-lookup"><span data-stu-id="1f630-129">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 <span data-ttu-id="1f630-130">Muestra cómo declarar y utilizar eventos.</span><span class="sxs-lookup"><span data-stu-id="1f630-130">Shows how to declare and use events.</span></span>  
  
 [<span data-ttu-id="1f630-131">Interfaces</span><span class="sxs-lookup"><span data-stu-id="1f630-131">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 <span data-ttu-id="1f630-132">Describe qué son las interfaces y cómo usarlas en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1f630-132">Describes what interfaces are and how you can use them in your applications.</span></span>  
  
 [<span data-ttu-id="1f630-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="1f630-133">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="1f630-134">Proporciona vínculos a temas que presentan la programación y las características de [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f630-134">Provides links to topics that introduce [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] features and programming.</span></span>  
  
 [<span data-ttu-id="1f630-135">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="1f630-135">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 <span data-ttu-id="1f630-136">Proporciona información general sobre objetos y clases, cómo se utilizan, las relaciones que mantienen entre sí y las propiedades, los métodos y los eventos que exponen.</span><span class="sxs-lookup"><span data-stu-id="1f630-136">Provides an overview of objects and classes, how they are used, their relationships to each other, and the properties, methods, and events they expose.</span></span>  
  
 [<span data-ttu-id="1f630-137">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="1f630-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 <span data-ttu-id="1f630-138">Describe los elementos de código que manipulan elementos que contienen valores, cómo utilizarlos de forma eficaz y cómo combinarlos para producir nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="1f630-138">Describes the code elements that manipulate value-holding elements, how to use them efficiently, and how to combine them to yield new values.</span></span>  
  
 [<span data-ttu-id="1f630-139">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="1f630-139">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 <span data-ttu-id="1f630-140">Describe los procedimientos `Sub`, `Function`, `Property` y `Operator`, así como temas avanzados, como procedimientos recursivos y sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="1f630-140">Describes `Sub`, `Function`, `Property`, and `Operator` procedures, as well as advanced topics such as recursive and overloaded procedures.</span></span>  
  
 [<span data-ttu-id="1f630-141">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="1f630-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 <span data-ttu-id="1f630-142">Describe las instrucciones de declaración y ejecutables.</span><span class="sxs-lookup"><span data-stu-id="1f630-142">Describes declaration and executable statements.</span></span>  
  
 [<span data-ttu-id="1f630-143">Cadenas</span><span class="sxs-lookup"><span data-stu-id="1f630-143">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 <span data-ttu-id="1f630-144">Proporciona vínculos a temas que describen los conceptos básicos sobre el uso de cadenas en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f630-144">Provides links to topics that describe the basic concepts about using strings in Visual Basic.</span></span>  
  
 [<span data-ttu-id="1f630-145">Variables</span><span class="sxs-lookup"><span data-stu-id="1f630-145">Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/index.md)  
 <span data-ttu-id="1f630-146">Presenta las variables y describe cómo utilizarlas en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f630-146">Introduces variables and describes how to use them in Visual Basic.</span></span>  
  
 [<span data-ttu-id="1f630-147">XML</span><span class="sxs-lookup"><span data-stu-id="1f630-147">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="1f630-148">Proporciona vínculos a temas en los que se describe cómo usar XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f630-148">Provides links to topics that describe how to use XML in Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1f630-149">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1f630-149">Related Sections</span></span>  
 [<span data-ttu-id="1f630-150">Colecciones</span><span class="sxs-lookup"><span data-stu-id="1f630-150">Collections</span></span>](https://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 <span data-ttu-id="1f630-151">Describe algunos de los tipos de colecciones proporcionadas por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f630-151">Describes some of the types of collections that are provided by the .NET Framework.</span></span> <span data-ttu-id="1f630-152">Muestra cómo usar colecciones sencillas y colecciones de pares clave-valor.</span><span class="sxs-lookup"><span data-stu-id="1f630-152">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>  
  
 [<span data-ttu-id="1f630-153">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f630-153">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 <span data-ttu-id="1f630-154">Proporciona información de referencia sobre diversos aspectos de programación en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f630-154">Provides reference information on various aspects of Visual Basic programming.</span></span>
