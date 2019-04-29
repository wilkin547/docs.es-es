---
title: Diseño de structs
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: KrzysztofCwalina
ms.openlocfilehash: cc5b8d7effda31b0236477b217bccf5cf2137f8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650146"
---
# <a name="struct-design"></a><span data-ttu-id="cde8d-102">Diseño de structs</span><span class="sxs-lookup"><span data-stu-id="cde8d-102">Struct Design</span></span>
<span data-ttu-id="cde8d-103">El tipo de valor de uso general más a menudo se conoce como una estructura, su palabra clave de C#.</span><span class="sxs-lookup"><span data-stu-id="cde8d-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="cde8d-104">Esta sección proporciona instrucciones para el diseño de la estructura general.</span><span class="sxs-lookup"><span data-stu-id="cde8d-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="cde8d-105">**X DO NOT** proporcionar un constructor predeterminado para un struct.</span><span class="sxs-lookup"><span data-stu-id="cde8d-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="cde8d-106">Seguir esta directriz permite que las matrices de structs crearse sin tener que ejecutar el constructor en cada elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cde8d-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="cde8d-107">Tenga en cuenta que C# no permite que las estructuras tienen constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="cde8d-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="cde8d-108">**X DO NOT** definir tipos de valor mutable.</span><span class="sxs-lookup"><span data-stu-id="cde8d-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="cde8d-109">Tipos de valor mutable tienen varios problemas.</span><span class="sxs-lookup"><span data-stu-id="cde8d-109">Mutable value types have several problems.</span></span> <span data-ttu-id="cde8d-110">Por ejemplo, un captador de propiedad que devuelve un tipo de valor, el llamador recibe una copia.</span><span class="sxs-lookup"><span data-stu-id="cde8d-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="cde8d-111">Dado que la copia se crea implícitamente, los desarrolladores podrían no ser consciente de que son una mutación de la copia y no el valor original.</span><span class="sxs-lookup"><span data-stu-id="cde8d-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="cde8d-112">Además, algunos lenguajes (lenguajes dinámicos, en particular) tienen problemas con los tipos de valor mutable porque incluso las variables locales, cuando se desreferencia, hacer una copia en realizarse.</span><span class="sxs-lookup"><span data-stu-id="cde8d-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="cde8d-113">**✓ DO** asegurarse de que un estado donde todos los datos de la instancia se establece en cero, false o null (según corresponda) es válido.</span><span class="sxs-lookup"><span data-stu-id="cde8d-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="cde8d-114">Esto evita la creación accidental de instancias no válidas cuando se crea una matriz de las estructuras.</span><span class="sxs-lookup"><span data-stu-id="cde8d-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="cde8d-115">**✓ DO** implementar <xref:System.IEquatable%601> en tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="cde8d-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="cde8d-116">El <xref:System.Object.Equals%2A?displayProperty=nameWithType> boxing hace que el método en tipos de valor y su implementación predeterminada no es muy eficaz, porque usa la reflexión.</span><span class="sxs-lookup"><span data-stu-id="cde8d-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="cde8d-117"><xref:System.IEquatable%601.Equals%2A> puede tener un rendimiento mucho mejor y se puede implementar para que no provocará la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="cde8d-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="cde8d-118">**X DO NOT** extender explícitamente <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="cde8d-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="cde8d-119">De hecho, la mayoría de los lenguajes evitar esto.</span><span class="sxs-lookup"><span data-stu-id="cde8d-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="cde8d-120">En general, los structs pueden ser muy útiles pero solo debe usarse para valores pequeños, únicos, inmutable que no se copia por boxing con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="cde8d-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="cde8d-121">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="cde8d-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="cde8d-122">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="cde8d-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde8d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="cde8d-123">See also</span></span>

- [<span data-ttu-id="cde8d-124">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="cde8d-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="cde8d-125">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cde8d-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="cde8d-126">Elección entre clase y estructura</span><span class="sxs-lookup"><span data-stu-id="cde8d-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
