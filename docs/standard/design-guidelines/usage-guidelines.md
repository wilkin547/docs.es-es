---
title: Instrucciones de uso
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: 03eaba3e52cb25619f65637efb4f414c22770440
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291349"
---
# <a name="usage-guidelines"></a><span data-ttu-id="593ff-102">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="593ff-102">Usage guidelines</span></span>

<span data-ttu-id="593ff-103">Esta sección contiene instrucciones para usar tipos comunes en las API de acceso público.</span><span class="sxs-lookup"><span data-stu-id="593ff-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="593ff-104">Trata el uso directo de tipos de marco de trabajo integrados (por ejemplo, atributos de serialización) y la sobrecarga de operadores comunes.</span><span class="sxs-lookup"><span data-stu-id="593ff-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="593ff-105">La <xref:System.IDisposable?displayProperty=nameWithType> interfaz no se trata en esta sección, pero se describe en la sección [patrón de Dispose](../garbage-collection/implementing-dispose.md) .</span><span class="sxs-lookup"><span data-stu-id="593ff-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="593ff-106">Para obtener instrucciones e información adicional sobre otros tipos de .NET Framework comunes integrados, vea los temas de referencia para lo siguiente: <xref:System.DateTime?displayProperty=nameWithType> , <xref:System.DateTimeOffset?displayProperty=nameWithType> , <xref:System.ICloneable?displayProperty=nameWithType> , <xref:System.IComparable%601?displayProperty=nameWithType> , <xref:System.IEquatable%601?displayProperty=nameWithType> , <xref:System.Nullable%601?displayProperty=nameWithType> , <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="593ff-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="593ff-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="593ff-107">In this section</span></span>

[<span data-ttu-id="593ff-108">Matrices</span><span class="sxs-lookup"><span data-stu-id="593ff-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="593ff-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="593ff-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="593ff-110">Recopilaciones</span><span class="sxs-lookup"><span data-stu-id="593ff-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="593ff-111">Serialización</span><span class="sxs-lookup"><span data-stu-id="593ff-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="593ff-112">Uso de System. XML</span><span class="sxs-lookup"><span data-stu-id="593ff-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="593ff-113">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="593ff-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="593ff-114">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="593ff-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="593ff-115">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="593ff-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="593ff-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="593ff-116">See also</span></span>

- [<span data-ttu-id="593ff-117">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="593ff-117">Framework Design Guidelines</span></span>](index.md)
