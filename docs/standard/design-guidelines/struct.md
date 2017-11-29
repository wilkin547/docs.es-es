---
title: "Diseño de structs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1566d2b67e1dda5b0b221a2c10affb6bdaea888
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="struct-design"></a><span data-ttu-id="00125-102">Diseño de structs</span><span class="sxs-lookup"><span data-stu-id="00125-102">Struct Design</span></span>
<span data-ttu-id="00125-103">El tipo de valor de uso general más a menudo se conoce como un struct, la palabra clave de C#.</span><span class="sxs-lookup"><span data-stu-id="00125-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="00125-104">Esta sección proporciona instrucciones para el diseño de la estructura general.</span><span class="sxs-lookup"><span data-stu-id="00125-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="00125-105">**X DO NOT** proporcionar un constructor predeterminado para un struct.</span><span class="sxs-lookup"><span data-stu-id="00125-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="00125-106">Seguir esta directriz permite matrices de structs crearse sin tener que ejecutar el constructor en cada elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="00125-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="00125-107">Tenga en cuenta que C# no permite estructuras tengan constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="00125-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="00125-108">**X DO NOT** definir tipos de valor mutable.</span><span class="sxs-lookup"><span data-stu-id="00125-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="00125-109">Tipos de valor mutable tienen varios problemas.</span><span class="sxs-lookup"><span data-stu-id="00125-109">Mutable value types have several problems.</span></span> <span data-ttu-id="00125-110">Por ejemplo, cuando un captador de propiedad devuelve un tipo de valor, el llamador recibe una copia.</span><span class="sxs-lookup"><span data-stu-id="00125-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="00125-111">Dado que la copia se crea implícitamente, los desarrolladores no sea consciente de que se Muta la copia y no el valor original.</span><span class="sxs-lookup"><span data-stu-id="00125-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="00125-112">Además, algunos lenguajes (lenguajes dinámicos, en particular) tienen problemas al utilizar tipos de valor mutable porque incluso las variables locales, cuando se desreferencia, hacer una copia en realizarse.</span><span class="sxs-lookup"><span data-stu-id="00125-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="00125-113">**✓ HACER** asegurarse de que un estado donde todos los datos de la instancia se establece en cero, false o null (según corresponda) es válido.</span><span class="sxs-lookup"><span data-stu-id="00125-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="00125-114">Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de las estructuras.</span><span class="sxs-lookup"><span data-stu-id="00125-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="00125-115">**✓ HACER** implementar <xref:System.IEquatable%601> en tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="00125-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="00125-116">El <xref:System.Object.Equals%2A?displayProperty=nameWithType> método en tipos de valor provoca conversión boxing y la implementación predeterminada no es muy eficaz, ya que usa la reflexión.</span><span class="sxs-lookup"><span data-stu-id="00125-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="00125-117"><xref:System.IEquatable%601.Equals%2A>puede tener un rendimiento mucho mejor y se puede implementar para que no producirá la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="00125-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="00125-118">**X DO NOT** extender explícitamente <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="00125-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="00125-119">De hecho, la mayoría de los lenguajes evitar esto.</span><span class="sxs-lookup"><span data-stu-id="00125-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="00125-120">En general, las estructuras pueden ser muy útiles, pero solo deben usarse para los valores pequeños, únicos e inmutable que no se realizar la conversión boxing con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="00125-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="00125-121">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="00125-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="00125-122">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="00125-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00125-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="00125-123">See Also</span></span>  
 [<span data-ttu-id="00125-124">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="00125-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="00125-125">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="00125-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="00125-126">Elegir entre clases y estructuras</span><span class="sxs-lookup"><span data-stu-id="00125-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
