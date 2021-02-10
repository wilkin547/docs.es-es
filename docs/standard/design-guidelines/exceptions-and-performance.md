---
description: 'Más información acerca de: Excepciones y rendimiento'
title: Excepciones y rendimiento
ms.date: 10/22/2008
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
ms.openlocfilehash: 72b35ccca5514e56dcc04fc0a07d1f9887c4a2f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642128"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="8ea97-103">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="8ea97-103">Exceptions and Performance</span></span>

<span data-ttu-id="8ea97-104">Un problema común relacionado con las excepciones es que si se usan excepciones para el código que genera errores de forma rutinaria, el rendimiento de la implementación será inaceptable.</span><span class="sxs-lookup"><span data-stu-id="8ea97-104">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="8ea97-105">Tiene sentido que exista esta preocupación.</span><span class="sxs-lookup"><span data-stu-id="8ea97-105">This is a valid concern.</span></span> <span data-ttu-id="8ea97-106">Cuando un miembro genera una excepción, su rendimiento puede ser más lento.</span><span class="sxs-lookup"><span data-stu-id="8ea97-106">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="8ea97-107">Sin embargo, es posible conseguir un buen rendimiento al tiempo que se respetan estrictamente las instrucciones de excepción que no permiten el uso de códigos de error.</span><span class="sxs-lookup"><span data-stu-id="8ea97-107">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="8ea97-108">Dos patrones que se describen en esta sección sugieren varias formas de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8ea97-108">Two patterns described in this section suggest ways to do this.</span></span>

 <span data-ttu-id="8ea97-109">❌ NO utilice códigos de error debido a que las excepciones podrían afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8ea97-109">❌ DO NOT use error codes because of concerns that exceptions might affect performance negatively.</span></span>

 <span data-ttu-id="8ea97-110">Para mejorar el rendimiento, es posible usar el patrón tester-doer o el patrón try-parse, que se describen en las dos secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="8ea97-110">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>

## <a name="tester-doer-pattern"></a><span data-ttu-id="8ea97-111">Patrón tester-doer</span><span class="sxs-lookup"><span data-stu-id="8ea97-111">Tester-Doer Pattern</span></span>

 <span data-ttu-id="8ea97-112">A veces, el rendimiento de un miembro de generación de excepciones se puede mejorar dividiéndolo en dos.</span><span class="sxs-lookup"><span data-stu-id="8ea97-112">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="8ea97-113">Echemos un vistazo al método <xref:System.Collections.Generic.ICollection%601.Add%2A> de la interfaz <xref:System.Collections.Generic.ICollection%601>.</span><span class="sxs-lookup"><span data-stu-id="8ea97-113">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 <span data-ttu-id="8ea97-114">El método `Add` se inicia si la colección es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8ea97-114">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="8ea97-115">Puede tratarse de un problema de rendimiento en escenarios en los que se espera que la llamada de método no se realice con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="8ea97-115">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="8ea97-116">Una de las formas de mitigar el problema consiste en probar si se puede escribir en la colección antes de intentar agregar un valor.</span><span class="sxs-lookup"><span data-stu-id="8ea97-116">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 <span data-ttu-id="8ea97-117">El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly`, se conoce como "evaluador".</span><span class="sxs-lookup"><span data-stu-id="8ea97-117">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="8ea97-118">Al miembro que se utiliza para realizar una operación potencialmente generadora de excepciones, el método `Add` en nuestro ejemplo, se le conoce como "doer".</span><span class="sxs-lookup"><span data-stu-id="8ea97-118">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>

 <span data-ttu-id="8ea97-119">✔️ Recomendamos el patrón tester-doer para los miembros que podrían generar excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="8ea97-119">✔️ CONSIDER the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

## <a name="try-parse-pattern"></a><span data-ttu-id="8ea97-120">Patrón try-parse</span><span class="sxs-lookup"><span data-stu-id="8ea97-120">Try-Parse Pattern</span></span>

 <span data-ttu-id="8ea97-121">En el caso de las API extremadamente sensibles al rendimiento, se debe usar un patrón aún más rápido que el patrón tester-doer descrito en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="8ea97-121">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="8ea97-122">El patrón realiza llamadas para ajustar el nombre de los miembros con el fin de convertir un caso de prueba bien definido en una parte de la semántica de los miembros.</span><span class="sxs-lookup"><span data-stu-id="8ea97-122">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="8ea97-123">Por ejemplo, <xref:System.DateTime> define un método <xref:System.DateTime.Parse%2A> que genera una excepción si se produce un error en el análisis de una cadena.</span><span class="sxs-lookup"><span data-stu-id="8ea97-123">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="8ea97-124">También define un método <xref:System.DateTime.TryParse%2A> correspondiente que intenta analizar, pero devuelve el valor false si el análisis no se realiza correctamente, y el resultado de un análisis correcto mediante un parámetro `out`.</span><span class="sxs-lookup"><span data-stu-id="8ea97-124">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>

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

 <span data-ttu-id="8ea97-125">Al usar este patrón, es importante definir la funcionalidad try en términos estrictos.</span><span class="sxs-lookup"><span data-stu-id="8ea97-125">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="8ea97-126">Si se produce un error en el miembro por cualquier motivo que no sea la funcionalidad try bien definida, el miembro todavía debería generar una excepción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8ea97-126">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>

 <span data-ttu-id="8ea97-127">✔️ Recomendamos el patrón try-parse para los miembros que podrían generar excepciones en escenarios comunes para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="8ea97-127">✔️ CONSIDER the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>

 <span data-ttu-id="8ea97-128">✔️ Use el prefijo "try" y el tipo de valor devuelto booleano para los métodos que implementan este patrón.</span><span class="sxs-lookup"><span data-stu-id="8ea97-128">✔️ DO use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>

 <span data-ttu-id="8ea97-129">✔️ Proporcione un miembro de generación de excepciones para cada miembro mediante el patrón try-parse.</span><span class="sxs-lookup"><span data-stu-id="8ea97-129">✔️ DO provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>

 <span data-ttu-id="8ea97-130">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="8ea97-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="8ea97-131">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="8ea97-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="8ea97-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ea97-132">See also</span></span>

- [<span data-ttu-id="8ea97-133">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8ea97-133">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="8ea97-134">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="8ea97-134">Design Guidelines for Exceptions</span></span>](exceptions.md)
