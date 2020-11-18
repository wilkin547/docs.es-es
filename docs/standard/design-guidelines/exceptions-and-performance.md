---
title: Excepciones y rendimiento
ms.date: 10/22/2008
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: 1d9e4ff3cfb02b1db358c19786322622621329fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821208"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="bc8e3-102">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="bc8e3-102">Exceptions and Performance</span></span>
<span data-ttu-id="bc8e3-103">Un problema común relacionado con las excepciones es que si se usan excepciones para el código que genera un error de forma rutinaria, el rendimiento de la implementación será inaceptable.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="bc8e3-104">Tiene sentido que exista esta preocupación.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-104">This is a valid concern.</span></span> <span data-ttu-id="bc8e3-105">Cuando un miembro produce una excepción, su rendimiento puede ser un orden de magnitud más lento.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="bc8e3-106">Sin embargo, es posible lograr un buen rendimiento al tiempo que se respetan estrictamente las instrucciones de excepción que no permiten el uso de códigos de error.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="bc8e3-107">Dos patrones que se describen en esta sección sugieren maneras de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-107">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="bc8e3-108">❌ No utilice códigos de error debido a las preocupaciones de que las excepciones podrían afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-108">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="bc8e3-109">Para mejorar el rendimiento, es posible usar el patrón Tester-Doer o el patrón Try-Parse, que se describe en las dos secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="bc8e3-110">Patrón de Tester-Doer</span><span class="sxs-lookup"><span data-stu-id="bc8e3-110">Tester-Doer Pattern</span></span>
 <span data-ttu-id="bc8e3-111">A veces, el rendimiento de un miembro de generación de excepciones se puede mejorar dividiendo el miembro en dos.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="bc8e3-112">Echemos un vistazo al <xref:System.Collections.Generic.ICollection%601.Add%2A> método de la <xref:System.Collections.Generic.ICollection%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="bc8e3-113">El método `Add` produce si la colección es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="bc8e3-114">Puede tratarse de un problema de rendimiento en escenarios en los que se espera que la llamada al método no se realice con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="bc8e3-115">Una de las formas de mitigar el problema consiste en probar si se puede escribir en la colección antes de intentar agregar un valor.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="bc8e3-116">El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly` , se conoce como evaluador.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="bc8e3-117">El miembro que se utiliza para realizar una operación de inicio potencial, el `Add` método en nuestro ejemplo, se conoce como doer.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="bc8e3-118">✔️ CONSIDERE el patrón de Tester-Doer de los miembros que pueden producir excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-118">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="bc8e3-119">Patrón de Try-Parse</span><span class="sxs-lookup"><span data-stu-id="bc8e3-119">Try-Parse Pattern</span></span>
 <span data-ttu-id="bc8e3-120">En el caso de las API extremadamente sensibles al rendimiento, se debe usar un patrón aún más rápido que el patrón de Tester-Doer descrito en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="bc8e3-121">El patrón llama a para ajustar el nombre del miembro con el fin de convertir un caso de prueba bien definido en una parte de la semántica de los miembros.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="bc8e3-122">Por ejemplo, <xref:System.DateTime> define un <xref:System.DateTime.Parse%2A> método que produce una excepción si se produce un error en el análisis de una cadena.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="bc8e3-123">También define un método correspondiente <xref:System.DateTime.TryParse%2A> que intenta analizar, pero devuelve false si el análisis no se realiza correctamente y devuelve el resultado de un análisis correcto mediante un `out` parámetro.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 <span data-ttu-id="bc8e3-124">Al usar este patrón, es importante definir la funcionalidad try en términos estrictos.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="bc8e3-125">Si se produce un error en el miembro por cualquier motivo que no sea el try bien definido, el miembro todavía debe producir una excepción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="bc8e3-126">✔️ CONSIDERE el patrón de Try-Parse de los miembros que pueden producir excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-126">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="bc8e3-127">✔️ usar el prefijo "Try" y el tipo de valor devuelto booleano para los métodos que implementan este patrón.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-127">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="bc8e3-128">✔️ proporcionan un miembro de generación de excepciones para cada miembro mediante el patrón de Try-Parse.</span><span class="sxs-lookup"><span data-stu-id="bc8e3-128">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="bc8e3-129">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="bc8e3-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="bc8e3-130">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="bc8e3-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="bc8e3-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc8e3-131">See also</span></span>

- [<span data-ttu-id="bc8e3-132">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="bc8e3-132">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="bc8e3-133">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="bc8e3-133">Design Guidelines for Exceptions</span></span>](exceptions.md)
