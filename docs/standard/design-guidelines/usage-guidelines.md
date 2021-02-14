---
description: 'Más información acerca de: Instrucciones de uso'
title: Instrucciones de uso
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: a435fab2adb00f671dfde1619a3c1f8db719d9df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641803"
---
# <a name="usage-guidelines"></a><span data-ttu-id="c4c72-103">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="c4c72-103">Usage guidelines</span></span>

<span data-ttu-id="c4c72-104">Esta sección contiene instrucciones para usar tipos comunes en las API de acceso público.</span><span class="sxs-lookup"><span data-stu-id="c4c72-104">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="c4c72-105">Trata sobre el uso directo de tipos de marco integrados (por ejemplo, atributos de serialización) y la sobrecarga de operadores comunes.</span><span class="sxs-lookup"><span data-stu-id="c4c72-105">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="c4c72-106">La interfaz de <xref:System.IDisposable?displayProperty=nameWithType> no se trata en esta sección, pero se describe en la sección [Patrón de eliminación](../garbage-collection/implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="c4c72-106">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="c4c72-107">Para obtener instrucciones e información adicional sobre otros tipos de .NET Framework comunes integrados, vea los temas de referencia para lo siguiente: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4c72-107">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c4c72-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c4c72-108">In this section</span></span>

[<span data-ttu-id="c4c72-109">Matrices</span><span class="sxs-lookup"><span data-stu-id="c4c72-109">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="c4c72-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4c72-110">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="c4c72-111">Colecciones</span><span class="sxs-lookup"><span data-stu-id="c4c72-111">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="c4c72-112">Serialización</span><span class="sxs-lookup"><span data-stu-id="c4c72-112">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="c4c72-113">Uso de System.Xml</span><span class="sxs-lookup"><span data-stu-id="c4c72-113">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="c4c72-114">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="c4c72-114">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="c4c72-115">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="c4c72-115">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="c4c72-116">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="c4c72-116">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4c72-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4c72-117">See also</span></span>

- [<span data-ttu-id="c4c72-118">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c4c72-118">Framework Design Guidelines</span></span>](index.md)
