---
title: Analizar cadenas en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: e4bf14981e538d95aebac3b0f36d38b61747989f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73084313"
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="dd8c1-102">Analizar cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="dd8c1-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="dd8c1-103">Una operación de análisis convierte una cadena que representa un tipo base de .NET en dicho tipo base.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="dd8c1-104">Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="dd8c1-105">El método que se usa normalmente para realizar una operación de análisis es el método `Parse`.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="dd8c1-106">Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="dd8c1-107">Del mismo modo que el formato usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para proporcionar información de formato según la referencia cultural, el análisis también usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para determinar cómo se interpreta una representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="dd8c1-108">Para obtener más información, consulte [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="dd8c1-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd8c1-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dd8c1-109">In This Section</span></span>  
 [<span data-ttu-id="dd8c1-110">Análisis de cadenas numéricas</span><span class="sxs-lookup"><span data-stu-id="dd8c1-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="dd8c1-111">Se describe cómo convertir cadenas en tipos numéricos de .NET.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="dd8c1-112">Análisis de cadenas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="dd8c1-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="dd8c1-113">Se describe cómo convertir cadenas en tipos **DateTime** de .NET.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="dd8c1-114">Análisis de otras cadenas</span><span class="sxs-lookup"><span data-stu-id="dd8c1-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="dd8c1-115">Se describe cómo convertir cadenas en tipos **carácter**, **booleano** y **enumeración**.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dd8c1-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="dd8c1-116">Related Sections</span></span>  
 [<span data-ttu-id="dd8c1-117">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="dd8c1-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="dd8c1-118">Se describen los conceptos de formato básicos, como especificadores de formato y proveedores de formato.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="dd8c1-119">Conversión de tipos en .NET</span><span class="sxs-lookup"><span data-stu-id="dd8c1-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="dd8c1-120">Se describe cómo convertir tipos.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="dd8c1-121">Tipos base</span><span class="sxs-lookup"><span data-stu-id="dd8c1-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="dd8c1-122">Se describen las operaciones comunes que se pueden realizar en tipos base de .NET.</span><span class="sxs-lookup"><span data-stu-id="dd8c1-122">Describes common operations that you can perform on .NET base types.</span></span>
