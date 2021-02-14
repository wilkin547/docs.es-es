---
description: 'Más información acerca de: Diseño de structs'
title: Diseño de structs
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: a28dd3e452d22e61d95ec521fdbde6539e38ed78
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641907"
---
# <a name="struct-design"></a><span data-ttu-id="e8c2e-103">Diseño de structs</span><span class="sxs-lookup"><span data-stu-id="e8c2e-103">Struct Design</span></span>

<span data-ttu-id="e8c2e-104">Normalmente, el tipo de valor de uso general se conoce como struct, su palabra clave en C#.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-104">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="e8c2e-105">En esta sección se proporcionan instrucciones para el diseño de estructuras generales.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-105">This section provides guidelines for general struct design.</span></span>

 <span data-ttu-id="e8c2e-106">❌ NO proporcione un constructor sin parámetros para un struct.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-106">❌ DO NOT provide a parameterless constructor for a struct.</span></span>

 <span data-ttu-id="e8c2e-107">La siguiente instrucción permite crear matrices de structs sin tener que ejecutar el constructor en cada elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-107">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="e8c2e-108">Tenga en cuenta que C# no permite que los structs tengan constructores sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-108">Notice that C# does not allow structs to have parameterless constructors.</span></span>

 <span data-ttu-id="e8c2e-109">❌ NO defina tipos de valores mutables.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-109">❌ DO NOT define mutable value types.</span></span>

 <span data-ttu-id="e8c2e-110">Los tipos de valores mutables tienen varios problemas.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-110">Mutable value types have several problems.</span></span> <span data-ttu-id="e8c2e-111">Por ejemplo, cuando un captador de propiedad devuelve un tipo de valor, el llamador recibe una copia.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-111">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="e8c2e-112">Dado que la copia se crea implícitamente, es posible que los desarrolladores no sean conscientes de que están mutando la copia y no el valor original.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-112">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="e8c2e-113">Además, algunos lenguajes (lenguajes dinámicos, en particular) tienen problemas al usar tipos de valores mutables porque incluso las variables locales, cuando se desreferencian, provocan una copia.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-113">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>

 <span data-ttu-id="e8c2e-114">✔️ DEBE asegurarse de que el estado donde todos los datos de instancia están establecidos en cero, falso o null (según corresponda) es válido.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-114">✔️ DO ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>

 <span data-ttu-id="e8c2e-115">Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de structs.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-115">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>

 <span data-ttu-id="e8c2e-116">✔️ DEBE implementar <xref:System.IEquatable%601> en tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-116">✔️ DO implement <xref:System.IEquatable%601> on value types.</span></span>

 <span data-ttu-id="e8c2e-117">El método <xref:System.Object.Equals%2A?displayProperty=nameWithType> en tipos de valor produce la conversión boxing y su implementación predeterminada no es muy eficaz, ya que utiliza la reflexión.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-117">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="e8c2e-118"><xref:System.IEquatable%601.Equals%2A> puede tener un rendimiento mucho mejor y se puede implementar para que no cause la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-118"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>

 <span data-ttu-id="e8c2e-119">❌ NO extienda explícitamente <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-119">❌ DO NOT explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="e8c2e-120">De hecho, la mayoría de los lenguajes lo impiden.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-120">In fact, most languages prevent this.</span></span>

 <span data-ttu-id="e8c2e-121">En general, los structs pueden ser muy útiles, pero solo se deben usar para los valores pequeños, únicos e inmutables a los que no se les aplicará la conversión boxing con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e8c2e-121">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>

 <span data-ttu-id="e8c2e-122">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="e8c2e-122">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="e8c2e-123">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="e8c2e-123">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="e8c2e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8c2e-124">See also</span></span>

- [<span data-ttu-id="e8c2e-125">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="e8c2e-125">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="e8c2e-126">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e8c2e-126">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="e8c2e-127">Elegir entre clases y structs</span><span class="sxs-lookup"><span data-stu-id="e8c2e-127">Choosing Between Class and Struct</span></span>](choosing-between-class-and-struct.md)
