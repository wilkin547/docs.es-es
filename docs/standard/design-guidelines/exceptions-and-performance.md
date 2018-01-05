---
title: Excepciones y rendimiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9a876a818086e0d54251f53a1e8f83cc74a574ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="exceptions-and-performance"></a><span data-ttu-id="014fe-102">Excepciones y rendimiento</span><span class="sxs-lookup"><span data-stu-id="014fe-102">Exceptions and Performance</span></span>
<span data-ttu-id="014fe-103">Una preocupación comunes relacionados con las excepciones es que si las excepciones se utilizan para el código que produce errores repetidamente, el rendimiento de la implementación es inaceptable.</span><span class="sxs-lookup"><span data-stu-id="014fe-103">One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance of the implementation will be unacceptable.</span></span> <span data-ttu-id="014fe-104">Se trata de una preocupación válida.</span><span class="sxs-lookup"><span data-stu-id="014fe-104">This is a valid concern.</span></span> <span data-ttu-id="014fe-105">Cuando un miembro produce una excepción, su rendimiento puede ser órdenes de magnitud más lento.</span><span class="sxs-lookup"><span data-stu-id="014fe-105">When a member throws an exception, its performance can be orders of magnitude slower.</span></span> <span data-ttu-id="014fe-106">Sin embargo, es posible lograr un buen rendimiento al estrictamente siguiendo las directrices de excepción que no permitir el uso de códigos de error.</span><span class="sxs-lookup"><span data-stu-id="014fe-106">However, it is possible to achieve good performance while strictly adhering to the exception guidelines that disallow using error codes.</span></span> <span data-ttu-id="014fe-107">Dos patrones que se describen en esta sección ofrecen sugerencias para hacer esto.</span><span class="sxs-lookup"><span data-stu-id="014fe-107">Two patterns described in this section suggest ways to do this.</span></span>  
  
 <span data-ttu-id="014fe-108">**X DO NOT** usar códigos de error debido a problemas que las excepciones pueden afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="014fe-108">**X DO NOT** use error codes because of concerns that exceptions might affect performance negatively.</span></span>  
  
 <span data-ttu-id="014fe-109">Para mejorar el rendimiento, es posible utilizar el patrón de acción de la herramienta de comprobación o el patrón de Try-análisis, se describe en las dos secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="014fe-109">To improve performance, it is possible to use either the Tester-Doer Pattern or the Try-Parse Pattern, described in the next two sections.</span></span>  
  
## <a name="tester-doer-pattern"></a><span data-ttu-id="014fe-110">Patrón de acción de la herramienta de comprobación</span><span class="sxs-lookup"><span data-stu-id="014fe-110">Tester-Doer Pattern</span></span>  
 <span data-ttu-id="014fe-111">A veces se puede mejorar el rendimiento de un miembro que inicie excepciones dividiendo el miembro en dos.</span><span class="sxs-lookup"><span data-stu-id="014fe-111">Sometimes performance of an exception-throwing member can be improved by breaking the member into two.</span></span> <span data-ttu-id="014fe-112">Echemos un vistazo a la <xref:System.Collections.Generic.ICollection%601.Add%2A> método de la <xref:System.Collections.Generic.ICollection%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="014fe-112">Let’s look at the <xref:System.Collections.Generic.ICollection%601.Add%2A> method of the <xref:System.Collections.Generic.ICollection%601> interface.</span></span>  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 <span data-ttu-id="014fe-113">El método `Add` produce si la colección es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="014fe-113">The method `Add` throws if the collection is read-only.</span></span> <span data-ttu-id="014fe-114">Esto puede ser un problema de rendimiento en escenarios donde se espera que la llamada al método producirá un error con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="014fe-114">This can be a performance problem in scenarios where the method call is expected to fail often.</span></span> <span data-ttu-id="014fe-115">Uno de los métodos para mitigar el problema es probar si la colección es de escritura antes de intentar agregar un valor.</span><span class="sxs-lookup"><span data-stu-id="014fe-115">One of the ways to mitigate the problem is to test whether the collection is writable before trying to add a value.</span></span>  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 <span data-ttu-id="014fe-116">El miembro que se usa para probar una condición, que en nuestro ejemplo es la propiedad `IsReadOnly`, se conoce como la herramienta de comprobación.</span><span class="sxs-lookup"><span data-stu-id="014fe-116">The member used to test a condition, which in our example is the property `IsReadOnly`, is referred to as the tester.</span></span> <span data-ttu-id="014fe-117">El miembro que se usa para realizar una operación potencialmente produce, la `Add` método en nuestro ejemplo, se conoce como la acción.</span><span class="sxs-lookup"><span data-stu-id="014fe-117">The member used to perform a potentially throwing operation, the `Add` method in our example, is referred to as the doer.</span></span>  
  
 <span data-ttu-id="014fe-118">**✓ Considere la posibilidad de** el patrón de acción de la herramienta de comprobación para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="014fe-118">**✓ CONSIDER** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
## <a name="try-parse-pattern"></a><span data-ttu-id="014fe-119">Patrón de try-análisis</span><span class="sxs-lookup"><span data-stu-id="014fe-119">Try-Parse Pattern</span></span>  
 <span data-ttu-id="014fe-120">Para las API de rendimiento es sumamente importante, debe utilizarse un patrón aun más rápido que el patrón de acción de la herramienta de comprobación se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="014fe-120">For extremely performance-sensitive APIs, an even faster pattern than the Tester-Doer Pattern described in the previous section should be used.</span></span> <span data-ttu-id="014fe-121">El patrón de las llamadas para ajustar el nombre del miembro para realizar una prueba bien definida caso una parte de la semántica de miembro.</span><span class="sxs-lookup"><span data-stu-id="014fe-121">The pattern calls for adjusting the member name to make a well-defined test case a part of the member semantics.</span></span> <span data-ttu-id="014fe-122">Por ejemplo, <xref:System.DateTime> define un <xref:System.DateTime.Parse%2A> método que produce una excepción si el análisis de una cadena se produce un error.</span><span class="sxs-lookup"><span data-stu-id="014fe-122">For example, <xref:System.DateTime> defines a <xref:System.DateTime.Parse%2A> method that throws an exception if parsing of a string fails.</span></span> <span data-ttu-id="014fe-123">También define un correspondiente <xref:System.DateTime.TryParse%2A> método que intenta analizar, pero devuelve false si el análisis es incorrecto y devuelve el resultado de una correcta con análisis un `out` parámetro.</span><span class="sxs-lookup"><span data-stu-id="014fe-123">It also defines a corresponding <xref:System.DateTime.TryParse%2A> method that attempts to parse, but returns false if parsing is unsuccessful and returns the result of a successful parsing using an `out` parameter.</span></span>  
  
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
  
 <span data-ttu-id="014fe-124">Al utilizar este patrón, es importante definir la funcionalidad de try en términos estrictos.</span><span class="sxs-lookup"><span data-stu-id="014fe-124">When using this pattern, it is important to define the try functionality in strict terms.</span></span> <span data-ttu-id="014fe-125">Si se produce un error en el miembro por cualquier razón distinta a la instrucción try bien definida, el miembro todavía debe producir una excepción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="014fe-125">If the member fails for any reason other than the well-defined try, the member must still throw a corresponding exception.</span></span>  
  
 <span data-ttu-id="014fe-126">**✓ Considere la posibilidad de** el patrón de Try-análisis para los miembros que pueden producir excepciones en común escenarios para evitar problemas de rendimiento relacionados con las excepciones.</span><span class="sxs-lookup"><span data-stu-id="014fe-126">**✓ CONSIDER** the Try-Parse Pattern for members that might throw exceptions in common scenarios to avoid performance problems related to exceptions.</span></span>  
  
 <span data-ttu-id="014fe-127">**✓ HACER** usar el prefijo "Try" y un valor booleano de tipo de valor devuelto para métodos de implementar este patrón.</span><span class="sxs-lookup"><span data-stu-id="014fe-127">**✓ DO** use the prefix "Try" and Boolean return type for methods implementing this pattern.</span></span>  
  
 <span data-ttu-id="014fe-128">**✓ HACER** proporcionan un miembro que inicie excepciones para cada miembro utilizando el modelo de análisis de Try.</span><span class="sxs-lookup"><span data-stu-id="014fe-128">**✓ DO** provide an exception-throwing member for each member using the Try-Parse Pattern.</span></span>  
  
 <span data-ttu-id="014fe-129">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="014fe-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="014fe-130">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="014fe-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014fe-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="014fe-131">See Also</span></span>  
 [<span data-ttu-id="014fe-132">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="014fe-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="014fe-133">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="014fe-133">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
