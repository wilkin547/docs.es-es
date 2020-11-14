---
title: Conversión de cadenas en tipos
description: Conozca el análisis de cadenas en .NET. El análisis convierte una cadena que representa un tipo base de .NET en ese tipo base. El análisis es la operación inversa de la aplicación de formato.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 3d23fa9c7ecc3593f03f70dbd5ea7bda841e8f4f
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400858"
---
# <a name="parse-strings-in-net"></a><span data-ttu-id="33400-105">Análisis de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="33400-105">Parse strings in .NET</span></span>

<span data-ttu-id="33400-106">Una operación de *análisis* convierte una cadena que representa un tipo base de .NET en dicho tipo base.</span><span class="sxs-lookup"><span data-stu-id="33400-106">A *parsing* operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="33400-107">Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="33400-107">For example, a parsing operation is used to convert a string to a floating-point number or to a date-and-time value.</span></span> <span data-ttu-id="33400-108">El método que se usa normalmente para realizar una operación de análisis es el método `Parse`.</span><span class="sxs-lookup"><span data-stu-id="33400-108">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="33400-109">Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones.</span><span class="sxs-lookup"><span data-stu-id="33400-109">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="33400-110">Del mismo modo que el formato usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para proporcionar información de formato según la referencia cultural, el análisis también usa un objeto que implementa la interfaz <xref:System.IFormatProvider> para determinar cómo se interpreta una representación de cadena.</span><span class="sxs-lookup"><span data-stu-id="33400-110">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="33400-111">Para más información, consulte [Tipos de formato](formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="33400-111">For more information, see [Format types](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="33400-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="33400-112">In This Section</span></span>
 <span data-ttu-id="33400-113">[Análisis de cadenas numéricas](parsing-numeric.md)</span><span class="sxs-lookup"><span data-stu-id="33400-113">[Parsing Numeric Strings](parsing-numeric.md)</span></span>\
 <span data-ttu-id="33400-114">Se describe cómo convertir cadenas en tipos numéricos de .NET.</span><span class="sxs-lookup"><span data-stu-id="33400-114">Describes how to convert strings into .NET numeric types.</span></span>

 <span data-ttu-id="33400-115">[Análisis de cadenas de fecha y hora](parsing-datetime.md)</span><span class="sxs-lookup"><span data-stu-id="33400-115">[Parsing Date and Time Strings](parsing-datetime.md)</span></span>\
 <span data-ttu-id="33400-116">Se describe cómo convertir cadenas en tipos **DateTime** de .NET.</span><span class="sxs-lookup"><span data-stu-id="33400-116">Describes how to convert strings into .NET **DateTime** types.</span></span>

 <span data-ttu-id="33400-117">[Análisis de otras cadenas](parsing-other.md)</span><span class="sxs-lookup"><span data-stu-id="33400-117">[Parsing Other Strings](parsing-other.md)</span></span>\
 <span data-ttu-id="33400-118">Se describe cómo convertir cadenas en tipos **carácter** , **booleano** y **enumeración**.</span><span class="sxs-lookup"><span data-stu-id="33400-118">Describes how to convert strings into **Char** , **Boolean** , and **Enum** types.</span></span>

## <a name="related-sections"></a><span data-ttu-id="33400-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="33400-119">Related Sections</span></span>
 <span data-ttu-id="33400-120">[Aplicar formato a tipos](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="33400-120">[Formatting Types](formatting-types.md)</span></span>\
 <span data-ttu-id="33400-121">Se describen los conceptos de formato básicos, como especificadores de formato y proveedores de formato.</span><span class="sxs-lookup"><span data-stu-id="33400-121">Describes basic formatting concepts like format specifiers and format providers.</span></span>

 <span data-ttu-id="33400-122">[Conversión de tipos en .NET](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="33400-122">[Type Conversion in .NET](type-conversion.md)</span></span>\
 <span data-ttu-id="33400-123">Se describe cómo convertir tipos.</span><span class="sxs-lookup"><span data-stu-id="33400-123">Describes how to convert types.</span></span>
