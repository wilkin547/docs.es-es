---
title: Instrucciones de uso
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02905c193387f78430ce1885449055060d07bf82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571038"
---
# <a name="usage-guidelines"></a><span data-ttu-id="9d80d-102">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="9d80d-102">Usage Guidelines</span></span>
<span data-ttu-id="9d80d-103">Esta sección contiene directrices para utilizar tipos comunes en las API es accesibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="9d80d-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="9d80d-104">Ocupa de uso directo de integrados tipos de marco de trabajo (por ejemplo, los atributos de serialización) y la sobrecarga de operadores comunes.</span><span class="sxs-lookup"><span data-stu-id="9d80d-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>  
  
 <span data-ttu-id="9d80d-105">El <xref:System.IDisposable?displayProperty=nameWithType> interfaz no se trata en esta sección, pero se describe en el [patrón Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) sección.</span><span class="sxs-lookup"><span data-stu-id="9d80d-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d80d-106">Para instrucciones e información adicional sobre otros comunes, los tipos integrados de .NET Framework, vea los temas de referencia para lo siguiente: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9d80d-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d80d-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9d80d-107">In This Section</span></span>  
 [<span data-ttu-id="9d80d-108">Matrices</span><span class="sxs-lookup"><span data-stu-id="9d80d-108">Arrays</span></span>](../../../docs/standard/design-guidelines/arrays.md)  
 [<span data-ttu-id="9d80d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9d80d-109">Attributes</span></span>](../../../docs/standard/design-guidelines/attributes.md)  
 [<span data-ttu-id="9d80d-110">Colecciones</span><span class="sxs-lookup"><span data-stu-id="9d80d-110">Collections</span></span>](/cpp/mfc/collections)  
 [<span data-ttu-id="9d80d-111">Serialización</span><span class="sxs-lookup"><span data-stu-id="9d80d-111">Serialization</span></span>](../../../docs/standard/design-guidelines/serialization.md)  
 [<span data-ttu-id="9d80d-112">Uso de System.Xml</span><span class="sxs-lookup"><span data-stu-id="9d80d-112">System.Xml Usage</span></span>](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [<span data-ttu-id="9d80d-113">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="9d80d-113">Equality Operators</span></span>](../../../docs/standard/design-guidelines/equality-operators.md)  
 <span data-ttu-id="9d80d-114">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="9d80d-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9d80d-115">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9d80d-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d80d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d80d-116">See Also</span></span>  
 [<span data-ttu-id="9d80d-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9d80d-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
