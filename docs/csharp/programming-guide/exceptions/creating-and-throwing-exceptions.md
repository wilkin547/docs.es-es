---
title: "Crear y producir excepciones (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
caps.latest.revision: 28
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
ms.openlocfilehash: 5f49b0911aa94480988987f209bc73d187451620
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a><span data-ttu-id="75d8c-102">Crear y producir excepciones (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="75d8c-102">Creating and Throwing Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="75d8c-103">Las excepciones se usan para indicar que se ha producido un error mientras se ejecutaba el programa.</span><span class="sxs-lookup"><span data-stu-id="75d8c-103">Exceptions are used to indicate that an error has occurred while running the program.</span></span> <span data-ttu-id="75d8c-104">Se crean los objetos de excepción que describen un error y, luego, se *producen* con la palabra clave [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="75d8c-104">Exception objects that describe an error are created and then *thrown* with the [throw](../../../csharp/language-reference/keywords/throw.md) keyword.</span></span> <span data-ttu-id="75d8c-105">Después, el tiempo de ejecución busca el controlador de excepciones más compatible.</span><span class="sxs-lookup"><span data-stu-id="75d8c-105">The runtime then searches for the most compatible exception handler.</span></span>  
  
 <span data-ttu-id="75d8c-106">Los programadores deberían producir excepciones cuando una o varias de las siguientes condiciones sean verdaderas:</span><span class="sxs-lookup"><span data-stu-id="75d8c-106">Programmers should throw exceptions when one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="75d8c-107">El método no puede finalizar su funcionalidad definida.</span><span class="sxs-lookup"><span data-stu-id="75d8c-107">The method cannot complete its defined functionality.</span></span>  
  
     <span data-ttu-id="75d8c-108">Por ejemplo, si un parámetro de un método tiene un valor no válido:</span><span class="sxs-lookup"><span data-stu-id="75d8c-108">For example, if a parameter to a method has an invalid value:</span></span>  
  
     <span data-ttu-id="75d8c-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="75d8c-109">[!code-cs[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]</span></span>  
  
-   <span data-ttu-id="75d8c-110">Se realiza una llamada inadecuada a un objeto, en función del estado del objeto.</span><span class="sxs-lookup"><span data-stu-id="75d8c-110">An inappropriate call to an object is made, based on the object state.</span></span>  
  
     <span data-ttu-id="75d8c-111">Un ejemplo podría ser intentar escribir en un archivo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="75d8c-111">One example might be trying to write to a read-only file.</span></span> <span data-ttu-id="75d8c-112">En los casos en los que un estado de objeto no admite una operación, produzca una instancia de <xref:System.InvalidOperationException> o un objeto basado en una derivación de esta clase.</span><span class="sxs-lookup"><span data-stu-id="75d8c-112">In cases where an object state does not allow an operation, throw an instance of <xref:System.InvalidOperationException> or an object based on a derivation of this class.</span></span> <span data-ttu-id="75d8c-113">Este es un ejemplo de un método que genera un objeto <xref:System.InvalidOperationException>:</span><span class="sxs-lookup"><span data-stu-id="75d8c-113">This is an example of a method that throws an <xref:System.InvalidOperationException> object:</span></span>  
  
     <span data-ttu-id="75d8c-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="75d8c-114">[!code-cs[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]</span></span>  
  
-   <span data-ttu-id="75d8c-115">Cuando un argumento de un método genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="75d8c-115">When an argument to a method causes an exception.</span></span>  
  
     <span data-ttu-id="75d8c-116">En este caso, se debe detectar la excepción original y se debe crear una instancia de <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="75d8c-116">In this case, the original exception should be caught and an <xref:System.ArgumentException> instance should be created.</span></span> <span data-ttu-id="75d8c-117">La excepción original debe pasarse al constructor de <xref:System.ArgumentException> como el parámetro <xref:System.Exception.InnerException%2A>:</span><span class="sxs-lookup"><span data-stu-id="75d8c-117">The original exception should be passed to the constructor of the <xref:System.ArgumentException> as the <xref:System.Exception.InnerException%2A> parameter:</span></span>  
  
     <span data-ttu-id="75d8c-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="75d8c-118">[!code-cs[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="75d8c-119">Las excepciones contienen una propiedad denominada <xref:System.Exception.StackTrace%2A>.</span><span class="sxs-lookup"><span data-stu-id="75d8c-119">Exceptions contain a property named <xref:System.Exception.StackTrace%2A>.</span></span> <span data-ttu-id="75d8c-120">Esta cadena contiene el nombre de los métodos de la pila de llamadas actual, junto con el nombre de archivo y el número de la línea en la que se ha producido la excepción para cada método.</span><span class="sxs-lookup"><span data-stu-id="75d8c-120">This string contains the name of the methods on the current call stack, together with the file name and line number where the exception was thrown for each method.</span></span> <span data-ttu-id="75d8c-121">Common Language Runtime (CLR) crea automáticamente un objeto <xref:System.Exception.StackTrace%2A> desde el punto de la instrucción `throw`, de manera que todas las excepciones se deben producir desde el punto en el que debe comenzar el seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="75d8c-121">A <xref:System.Exception.StackTrace%2A> object is created automatically by the common language runtime (CLR) from the point of the `throw` statement, so that exceptions must be thrown from the point where the stack trace should begin.</span></span>  
  
 <span data-ttu-id="75d8c-122">Todas las excepciones contienen una propiedad denominada <xref:System.Exception.Message%2A>.</span><span class="sxs-lookup"><span data-stu-id="75d8c-122">All exceptions contain a property named <xref:System.Exception.Message%2A>.</span></span> <span data-ttu-id="75d8c-123">Esta cadena debe establecerse para que explique el motivo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="75d8c-123">This string should be set to explain the reason for the exception.</span></span> <span data-ttu-id="75d8c-124">Tenga en cuenta que no se debe colocar información confidencial en materia de seguridad en el texto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="75d8c-124">Note that information that is sensitive to security should not be put in the message text.</span></span> <span data-ttu-id="75d8c-125">Además de <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contiene una propiedad denominada <xref:System.ArgumentException.ParamName%2A> que debe establecerse en el nombre del argumento que ha provocado que se genere la excepción.</span><span class="sxs-lookup"><span data-stu-id="75d8c-125">In addition to <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contains a property named <xref:System.ArgumentException.ParamName%2A> that should be set to the name of the argument that caused the exception to be thrown.</span></span> <span data-ttu-id="75d8c-126">En el caso de un establecedor de propiedades, <xref:System.ArgumentException.ParamName%2A> debe establecerse en `value`.</span><span class="sxs-lookup"><span data-stu-id="75d8c-126">In the case of a property setter, <xref:System.ArgumentException.ParamName%2A> should be set to `value`.</span></span>  
  
 <span data-ttu-id="75d8c-127">Los miembros de métodos públicos y protegidos deben producir excepciones cada vez que no puedan finalizar sus funciones previstas.</span><span class="sxs-lookup"><span data-stu-id="75d8c-127">Public and protected methods members should throw exceptions whenever they cannot complete their intended functions.</span></span> <span data-ttu-id="75d8c-128">La clase de excepciones que se produce debe ser la excepción más específica disponible que se ajuste a las condiciones del error.</span><span class="sxs-lookup"><span data-stu-id="75d8c-128">The exception class that is thrown should be the most specific exception available that fits the error conditions.</span></span> <span data-ttu-id="75d8c-129">Estas excepciones se deben documentar como parte de la funcionalidad de la clase, y las clases derivadas o actualizaciones de la clase original deben mantener el mismo comportamiento para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="75d8c-129">These exceptions should be documented as part of the class functionality, and derived classes or updates to the original class should retain the same behavior for backward compatibility.</span></span>  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a><span data-ttu-id="75d8c-130">Aspectos que se deben evitar al producir excepciones</span><span class="sxs-lookup"><span data-stu-id="75d8c-130">Things to Avoid When Throwing Exceptions</span></span>  
 <span data-ttu-id="75d8c-131">En la siguiente lista se identifican los procedimientos que se deben evitar al producir excepciones:</span><span class="sxs-lookup"><span data-stu-id="75d8c-131">The following list identifies practices to avoid when throwing exceptions:</span></span>  
  
-   <span data-ttu-id="75d8c-132">Las excepciones no deben usarse para cambiar el flujo de un programa como parte de la ejecución normal.</span><span class="sxs-lookup"><span data-stu-id="75d8c-132">Exceptions should not be used to change the flow of a program as part of ordinary execution.</span></span> <span data-ttu-id="75d8c-133">Las excepciones solo deben usarse para comunicar y controlar las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="75d8c-133">Exceptions should only be used to report and handle error conditions.</span></span>  
  
-   <span data-ttu-id="75d8c-134">Las excepciones no se deben devolver como un parámetro o valor devuelto en lugar de producirse.</span><span class="sxs-lookup"><span data-stu-id="75d8c-134">Exceptions should not be returned as a return value or parameter instead of being thrown.</span></span>  
  
-   <span data-ttu-id="75d8c-135">No genere <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName> o <xref:System.IndexOutOfRangeException?displayProperty=fullName> de manera intencionada desde su propio código fuente.</span><span class="sxs-lookup"><span data-stu-id="75d8c-135">Do not throw <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, <xref:System.NullReferenceException?displayProperty=fullName>, or <xref:System.IndexOutOfRangeException?displayProperty=fullName> intentionally from your own source code.</span></span>  
  
-   <span data-ttu-id="75d8c-136">No cree excepciones que se puedan producir en el modo de depuración, pero no en el modo de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="75d8c-136">Do not create exceptions that can be thrown in debug mode but not release mode.</span></span> <span data-ttu-id="75d8c-137">Para identificar los errores en tiempo de ejecución durante la fase de desarrollo, use la aserción de depuración.</span><span class="sxs-lookup"><span data-stu-id="75d8c-137">To identify run-time errors during the development phase, use Debug Assert instead.</span></span>  
  
## <a name="defining-exception-classes"></a><span data-ttu-id="75d8c-138">Definir clases de excepción</span><span class="sxs-lookup"><span data-stu-id="75d8c-138">Defining Exception Classes</span></span>  
 <span data-ttu-id="75d8c-139">Los programas pueden producir una clase de excepción predefinida en el espacio de nombres <xref:System> (excepto en los casos indicados anteriormente) o crear sus propias clases de excepción mediante la derivación de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="75d8c-139">Programs can throw a predefined exception class in the <xref:System> namespace (except where previously noted), or create their own exception classes by deriving from <xref:System.Exception>.</span></span> <span data-ttu-id="75d8c-140">Las clases derivadas deben definir al menos cuatro constructores: un constructor predeterminado, uno que establezca la propiedad de mensaje y otro que establezca las propiedades <xref:System.Exception.Message%2A> y <xref:System.Exception.InnerException%2A>.</span><span class="sxs-lookup"><span data-stu-id="75d8c-140">The derived classes should define at least four constructors: one default constructor, one that sets the message property, and one that sets both the <xref:System.Exception.Message%2A> and <xref:System.Exception.InnerException%2A> properties.</span></span> <span data-ttu-id="75d8c-141">El cuarto constructor se usa para serializar la excepción.</span><span class="sxs-lookup"><span data-stu-id="75d8c-141">The fourth constructor is used to serialize the exception.</span></span> <span data-ttu-id="75d8c-142">Las nuevas clases de excepción deben ser serializables.</span><span class="sxs-lookup"><span data-stu-id="75d8c-142">New exception classes should be serializable.</span></span> <span data-ttu-id="75d8c-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75d8c-143">For example:</span></span>  
  
 <span data-ttu-id="75d8c-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="75d8c-144">[!code-cs[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="75d8c-145">Las nuevas propiedades solo deben agregarse a la clase de excepción cuando los datos que proporcionan son útiles para resolver la excepción.</span><span class="sxs-lookup"><span data-stu-id="75d8c-145">New properties should only be added to the exception class when the data they provide is useful to resolving the exception.</span></span> <span data-ttu-id="75d8c-146">Si se agregan nuevas propiedades a la clase de excepción derivada, se debe invalidar `ToString()` para devolver la información agregada.</span><span class="sxs-lookup"><span data-stu-id="75d8c-146">If new properties are added to the derived exception class, `ToString()` should be overridden to return the added information.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="75d8c-147">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="75d8c-147">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75d8c-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="75d8c-148">See Also</span></span>  
 <span data-ttu-id="75d8c-149">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="75d8c-149">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="75d8c-150">[Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="75d8c-150">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="75d8c-151">[Exception Hierarchy](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b)  (Jerarquía de excepciones)</span><span class="sxs-lookup"><span data-stu-id="75d8c-151">[Exception Hierarchy](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b) </span></span>  
 [<span data-ttu-id="75d8c-152">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="75d8c-152">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)

