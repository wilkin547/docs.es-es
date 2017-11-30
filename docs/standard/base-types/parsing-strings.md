---
title: Analizar cadenas en .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a><span data-ttu-id="17a0c-102">Analizar cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="17a0c-102">Parsing Strings in .NET</span></span>
<span data-ttu-id="17a0c-103">Una operación de análisis convierte una cadena que representa un tipo base de .NET en dicho tipo base.</span><span class="sxs-lookup"><span data-stu-id="17a0c-103">A parsing operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="17a0c-104">Por ejemplo, se usa una operación de análisis para convertir una cadena en un número de punto flotante o un valor de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="17a0c-104">For example, a parsing operation is used to convert a string to a floating-point number or to a date and time value.</span></span> <span data-ttu-id="17a0c-105">El método que se usa normalmente para realizar una operación de análisis es el método `Parse`.</span><span class="sxs-lookup"><span data-stu-id="17a0c-105">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="17a0c-106">Dado que el análisis es la operación inversa del formato (lo que implica convertir un tipo base en su representación de cadena), se aplican muchas de las mismas reglas y convenciones.</span><span class="sxs-lookup"><span data-stu-id="17a0c-106">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="17a0c-107">Al igual que el formato usa un objeto que implementa el <xref:System.IFormatProvider> interfaz para proporcionar información de formato de cuenta de la referencia cultural, análisis también utiliza un objeto que implementa el <xref:System.IFormatProvider> interfaz para determinar cómo interpretar una representación de cadena .</span><span class="sxs-lookup"><span data-stu-id="17a0c-107">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="17a0c-108">Para obtener más información, consulte [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="17a0c-108">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17a0c-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="17a0c-109">In This Section</span></span>  
 [<span data-ttu-id="17a0c-110">Análisis de cadenas numéricas</span><span class="sxs-lookup"><span data-stu-id="17a0c-110">Parsing Numeric Strings</span></span>](../../../docs/standard/base-types/parsing-numeric.md)  
 <span data-ttu-id="17a0c-111">Describe cómo convertir cadenas en tipos numéricos. NET.</span><span class="sxs-lookup"><span data-stu-id="17a0c-111">Describes how to convert strings into .NET numeric types.</span></span>  
  
 [<span data-ttu-id="17a0c-112">Análisis de cadenas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="17a0c-112">Parsing Date and Time Strings</span></span>](../../../docs/standard/base-types/parsing-datetime.md)  
 <span data-ttu-id="17a0c-113">Describe cómo convertir cadenas en .NET **DateTime** tipos.</span><span class="sxs-lookup"><span data-stu-id="17a0c-113">Describes how to convert strings into .NET **DateTime** types.</span></span>  
  
 [<span data-ttu-id="17a0c-114">Análisis de otras cadenas</span><span class="sxs-lookup"><span data-stu-id="17a0c-114">Parsing Other Strings</span></span>](../../../docs/standard/base-types/parsing-other.md)  
 <span data-ttu-id="17a0c-115">Describe cómo convertir cadenas en **Char**, **booleano**, y **Enum** tipos.</span><span class="sxs-lookup"><span data-stu-id="17a0c-115">Describes how to convert strings into **Char**, **Boolean**, and **Enum** types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="17a0c-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="17a0c-116">Related Sections</span></span>  
 [<span data-ttu-id="17a0c-117">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="17a0c-117">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="17a0c-118">Describe los conceptos básicos de formato como especificadores de formato y proveedores de formato.</span><span class="sxs-lookup"><span data-stu-id="17a0c-118">Describes basic formatting concepts like format specifiers and format providers.</span></span>  
  
 [<span data-ttu-id="17a0c-119">Conversión de tipos en .NET</span><span class="sxs-lookup"><span data-stu-id="17a0c-119">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="17a0c-120">Describe cómo se convierten a tipos.</span><span class="sxs-lookup"><span data-stu-id="17a0c-120">Describes how to convert types.</span></span>  
  
 [<span data-ttu-id="17a0c-121">Tipos base</span><span class="sxs-lookup"><span data-stu-id="17a0c-121">Base Types</span></span>](../../../docs/standard/base-types/index.md)  
 <span data-ttu-id="17a0c-122">Describe las operaciones habituales que pueden realizar en tipos base. NET.</span><span class="sxs-lookup"><span data-stu-id="17a0c-122">Describes common operations that you can perform on .NET base types.</span></span>
