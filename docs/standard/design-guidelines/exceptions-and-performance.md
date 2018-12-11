---
title: Excepciones y rendimiento
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: KrzysztofCwalina
ms.openlocfilehash: ab125117836545b9a2436347375ed0e08c591c7b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153753"
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="a9473-102">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="a9473-102">Exceptions and Performance</span></span>
<span data-ttu-id="a9473-103">Una preocupación comunes relacionados con las excepciones es que si las excepciones se utilizan para el código que habitualmente se produce un error, el rendimiento de la implementación será aceptable.</span><span class="sxs-lookup"><span data-stu-id="a9473-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="a9473-104">Esto es una preocupación válida.</span><span class="sxs-lookup"><span data-stu-id="a9473-104">This is a valid concern.</span></span> <span data-ttu-id="a9473-105">Cuando un miembro produce una excepción, su rendimiento puede ser órdenes de magnitud más lentas.</span><span class="sxs-lookup"><span data-stu-id="a9473-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="a9473-106">Sin embargo, es posible lograr un buen rendimiento al estrictamente siguiendo las instrucciones de la excepción que no permitir el uso de códigos de error.</span><span class="sxs-lookup"><span data-stu-id="a9473-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="a9473-107">Dos patrones descritos en esta sección sugieren formas para hacer esto.</span><span class="sxs-lookup"><span data-stu-id="a9473-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="a9473-108">**X DO NOT** usar códigos de error debido a problemas que las excepciones pueden afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a9473-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="a9473-109">Para mejorar el rendimiento, es posible usar Tester-Doer (modelo) o el patrón de Try Parse, se describe en las dos secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="a9473-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="a9473-110">Tester-Doer (modelo)</span><span class="sxs-lookup"><span data-stu-id="a9473-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="a9473-111">A veces se puede mejorar el rendimiento de un miembro de inicio de excepción dividiendo el miembro en dos.</span><span class="sxs-lookup"><span data-stu-id="a9473-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="a9473-112">Echemos un vistazo a la <xref:System.Collections.Generic.ICollection%601.Add%2A> método de la <xref:System.Collections.Generic.ICollection%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="a9473-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="a9473-113">El método `Add` se produce si la colección es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a9473-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="a9473-114">Esto puede ser un problema de rendimiento en escenarios donde se espera que la llamada al método producirá un error con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="a9473-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="a9473-115">Una de las formas de mitigar el problema es comprobar si la colección es de escritura antes de intentar agregar un valor.</span><span class="sxs-lookup"><span data-stu-id="a9473-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="a9473-116">El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly`, se conoce como la herramienta de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a9473-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="a9473-117">El miembro que se usa para realizar una operación potencialmente produce, la `Add` método en nuestro ejemplo, se conoce como parte de la acción.</span><span class="sxs-lookup"><span data-stu-id="a9473-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="a9473-118">**✓ CONSIDER** el patrón de acción de la herramienta de comprobación para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="a9473-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="a9473-119">Patrón de try Parse</span><span class="sxs-lookup"><span data-stu-id="a9473-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="a9473-120">Para las API extremadamente sensibles al rendimiento, se debe usar un patrón aún más rápido que el patrón de Tester-Doer descrito en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="a9473-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="a9473-121">El patrón se llama para ajustar el nombre de miembro para realizar una prueba bien definida caso una parte de la semántica de miembro.</span><span class="sxs-lookup"><span data-stu-id="a9473-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="a9473-122">Por ejemplo, <xref:System.DateTime> define un <xref:System.DateTime.Parse%2A> método que produce una excepción si el análisis de una cadena se produce un error.</span><span class="sxs-lookup"><span data-stu-id="a9473-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="a9473-123">También define correspondiente <xref:System.DateTime.TryParse%2A> método que intenta analizar, pero devuelve false si el análisis es correcta y devuelve el resultado de una correcta con análisis un `out` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a9473-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="a9473-124">Al utilizar este patrón, es importante definir la funcionalidad de try en términos estrictos.</span><span class="sxs-lookup"><span data-stu-id="a9473-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="a9473-125">Si el miembro falla por alguna razón distinta try bien definida, el miembro todavía debe producir una excepción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a9473-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="a9473-126">**✓ CONSIDER** el patrón de Try-análisis para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="a9473-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="a9473-127">**✓ DO** usar el prefijo "Try" y un valor booleano de tipo de valor devuelto para métodos de implementar este patrón.</span><span class="sxs-lookup"><span data-stu-id="a9473-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="a9473-128">**✓ DO** proporcionan un miembro que inicie excepciones para cada miembro utilizando el modelo de análisis de Try.</span><span class="sxs-lookup"><span data-stu-id="a9473-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="a9473-129">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="a9473-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a9473-130">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="a9473-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9473-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9473-131">See also</span></span>

- [<span data-ttu-id="a9473-132">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9473-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="a9473-133">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="a9473-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
