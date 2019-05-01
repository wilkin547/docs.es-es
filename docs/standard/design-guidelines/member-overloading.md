---
title: Sobrecarga de miembro
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: b13f9e1551aec7e53ba1ac2ed0b9049d46b0a756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945552"
---
# <a name="member-overloading"></a><span data-ttu-id="b2233-102">Sobrecarga de miembro</span><span class="sxs-lookup"><span data-stu-id="b2233-102">Member Overloading</span></span>
<span data-ttu-id="b2233-103">Sobrecarga de miembro significa crear dos o más miembros en el mismo tipo que solo difieren en el número o tipo de parámetros, pero tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b2233-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="b2233-104">Por ejemplo, en la siguiente, el `WriteLine` método está sobrecargado:</span><span class="sxs-lookup"><span data-stu-id="b2233-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="b2233-105">Dado que solo los métodos, constructores y propiedades indizadas pueden tener parámetros, solo los miembros se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="b2233-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="b2233-106">La sobrecarga es una de las técnicas más importantes para mejorar la facilidad de uso, la productividad y mejorar la legibilidad de bibliotecas reutilizables.</span><span class="sxs-lookup"><span data-stu-id="b2233-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="b2233-107">La sobrecarga en el número de parámetros hace posible proporcionar versiones más sencillas de métodos y constructores.</span><span class="sxs-lookup"><span data-stu-id="b2233-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="b2233-108">La sobrecarga en el tipo de parámetro permite usar el mismo nombre de miembro para realizar operaciones idénticas en un conjunto seleccionado de diferentes tipos de miembros.</span><span class="sxs-lookup"><span data-stu-id="b2233-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="b2233-109">**✓ DO** intenta utilizar nombres de parámetros descriptivos para indicar el valor predeterminado utilizado por las sobrecargas más cortas.</span><span class="sxs-lookup"><span data-stu-id="b2233-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="b2233-110">**X AVOID** variar arbitrariamente los nombres de parámetro en las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="b2233-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="b2233-111">Si un parámetro de una sobrecarga representa la misma entrada como un parámetro en la otra sobrecarga, los parámetros deben tener el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b2233-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="b2233-112">**X AVOID** incoherente en el orden de los parámetros en sobrecarga los miembros.</span><span class="sxs-lookup"><span data-stu-id="b2233-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="b2233-113">Parámetros con el mismo nombre deberían aparecer en la misma posición en todas las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="b2233-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="b2233-114">**✓ DO** realizar virtual sólo la sobrecarga más larga (si se requiere la extensibilidad).</span><span class="sxs-lookup"><span data-stu-id="b2233-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="b2233-115">Las sobrecargas más cortas simplemente deben llamar a través de una sobrecarga mayor.</span><span class="sxs-lookup"><span data-stu-id="b2233-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="b2233-116">**X DO NOT** usar `ref` o `out` modificadores para sobrecargar los miembros.</span><span class="sxs-lookup"><span data-stu-id="b2233-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="b2233-117">Algunos lenguajes no pueden resolver llamadas a sobrecargas similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2233-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="b2233-118">Además, estas sobrecargas normalmente tienen una semántica completamente diferente y no deben ser las sobrecargas, pero dos métodos independientes en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b2233-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="b2233-119">**X DO NOT** tienen sobrecargas con parámetros en la misma posición que él y los tipos similares pero con una semántica diferente.</span><span class="sxs-lookup"><span data-stu-id="b2233-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="b2233-120">**✓ DO** permitir `null` que se pasarán para los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="b2233-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="b2233-121">**✓ DO** usar miembro sobrecarga en lugar de definir miembros con argumentos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b2233-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="b2233-122">Argumentos predeterminados no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="b2233-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="b2233-123">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="b2233-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b2233-124">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b2233-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2233-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2233-125">See also</span></span>

- [<span data-ttu-id="b2233-126">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="b2233-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="b2233-127">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b2233-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
