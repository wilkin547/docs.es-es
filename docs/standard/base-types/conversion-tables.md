---
title: "Tablas de conversión de tipos en .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- widening conversions
- narrowing conversions
- type conversion, table
- converting types, narrowing conversions
- converting types, widening conversions
- base types, converting
- tables [.NET Framework], type conversions
- data types [.NET Framework], converting
ms.assetid: 0ea65c59-85eb-4a52-94ca-c36d3bd13058
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327469f9a151b6ef7e1c42f6669c0a9dae7016fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-tables-in-net"></a><span data-ttu-id="d6dc8-102">Tablas de conversión de tipos en .NET</span><span class="sxs-lookup"><span data-stu-id="d6dc8-102">Type Conversion Tables in .NET</span></span>
<span data-ttu-id="d6dc8-103">Una conversión de ampliación se produce cuando se convierte un valor de un tipo a otro tipo que es de igual o mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-103">Widening conversion occurs when a value of one type is converted to another type that is of equal or greater size.</span></span> <span data-ttu-id="d6dc8-104">Una conversión de restricción se produce cuando se convierte un valor de un tipo a otro tipo que es de un tamaño menor.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-104">A narrowing conversion occurs when a value of one type is converted to a value of another type that is of a smaller size.</span></span> <span data-ttu-id="d6dc8-105">En las tablas de este tema se muestran los comportamientos de ambos tipos de conversiones.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-105">The tables in this topic illustrate the behaviors exhibited by both types of conversions.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="d6dc8-106">conversiones de ampliación</span><span class="sxs-lookup"><span data-stu-id="d6dc8-106">Widening Conversions</span></span>  
 <span data-ttu-id="d6dc8-107">La tabla siguiente describen las conversiones de ampliación que se pueden realizar sin pérdida de información.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-107">The following table describes the widening conversions that can be performed without the loss of information.</span></span>  
  
|<span data-ttu-id="d6dc8-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6dc8-108">Type</span></span>|<span data-ttu-id="d6dc8-109">Se puede convertir sin pérdida de datos a</span><span class="sxs-lookup"><span data-stu-id="d6dc8-109">Can be converted without data loss to</span></span>|  
|----------|-------------------------------------------|  
|<xref:System.Byte>|<span data-ttu-id="d6dc8-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d6dc8-110"><xref:System.UInt16>, <xref:System.Int16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.SByte>|<span data-ttu-id="d6dc8-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d6dc8-111"><xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="d6dc8-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d6dc8-112"><xref:System.Int32>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="d6dc8-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d6dc8-113"><xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Char>|<span data-ttu-id="d6dc8-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d6dc8-114"><xref:System.UInt16>, <xref:System.UInt32>, <xref:System.Int32>, <xref:System.UInt64>, <xref:System.Int64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="d6dc8-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d6dc8-115"><xref:System.Int64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="d6dc8-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d6dc8-116"><xref:System.Int64>, <xref:System.UInt64>, <xref:System.Double>, <xref:System.Decimal></span></span>|  
|<xref:System.Int64>|<xref:System.Decimal>|  
|<xref:System.UInt64>|<xref:System.Decimal>|  
|<xref:System.Single>|<xref:System.Double>|  
  
 <span data-ttu-id="d6dc8-117">Algunas conversiones a de ampliación <xref:System.Single> o <xref:System.Double> puede provocar una pérdida de precisión.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-117">Some widening conversions to <xref:System.Single> or <xref:System.Double> can cause a loss of precision.</span></span> <span data-ttu-id="d6dc8-118">En la tabla siguiente se describen las conversiones de ampliación que a veces se traducen en una pérdida de información.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-118">The following table describes the widening conversions that sometimes result in a loss of information.</span></span>  
  
|<span data-ttu-id="d6dc8-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6dc8-119">Type</span></span>|<span data-ttu-id="d6dc8-120">Se puede convertir a</span><span class="sxs-lookup"><span data-stu-id="d6dc8-120">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Int32>|<xref:System.Single>|  
|<xref:System.UInt32>|<xref:System.Single>|  
|<xref:System.Int64>|<span data-ttu-id="d6dc8-121"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="d6dc8-121"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="d6dc8-122"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="d6dc8-122"><xref:System.Single>, <xref:System.Double></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="d6dc8-123"><xref:System.Single>, <xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="d6dc8-123"><xref:System.Single>, <xref:System.Double></span></span>|  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="d6dc8-124">conversiones de restricción</span><span class="sxs-lookup"><span data-stu-id="d6dc8-124">Narrowing Conversions</span></span>  
 <span data-ttu-id="d6dc8-125">Una conversión de restricción a <xref:System.Single> o <xref:System.Double> puede provocar una pérdida de información.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-125">A narrowing conversion to <xref:System.Single> or <xref:System.Double> can cause a loss of information.</span></span> <span data-ttu-id="d6dc8-126">Si el tipo de destino no puede expresar correctamente la magnitud del origen, el tipo resultante se establece en la constante `PositiveInfinity` o `NegativeInfinity`.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-126">If the target type cannot properly express the magnitude of the source, the resulting type is set to the constant `PositiveInfinity` or `NegativeInfinity`.</span></span> <span data-ttu-id="d6dc8-127">`PositiveInfinity`el resultado de dividir un número positivo por cero y también se devuelve cuando el valor de un <xref:System.Single> o <xref:System.Double> supera el valor de la `MaxValue` campo.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-127">`PositiveInfinity` results from dividing a positive number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> exceeds the value of the `MaxValue` field.</span></span> <span data-ttu-id="d6dc8-128">`NegativeInfinity`el resultado de dividir un número negativo por cero y también se devuelve cuando el valor de un <xref:System.Single> o <xref:System.Double> cae por debajo del valor de la `MinValue` campo.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-128">`NegativeInfinity` results from dividing a negative number by zero and is also returned when the value of a <xref:System.Single> or <xref:System.Double> falls below the value of the `MinValue` field.</span></span> <span data-ttu-id="d6dc8-129">Una conversión de un <xref:System.Double> a una <xref:System.Single> puede dar lugar a `PositiveInfinity` o `NegativeInfinity`.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-129">A conversion from a <xref:System.Double> to a <xref:System.Single> might result in `PositiveInfinity` or `NegativeInfinity`.</span></span>  
  
 <span data-ttu-id="d6dc8-130">Una conversión de restricción también puede traducirse en una pérdida de información para otros tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-130">A narrowing conversion can also result in a loss of information for other data types.</span></span> <span data-ttu-id="d6dc8-131">Sin embargo, un <xref:System.OverflowException> se produce si el valor de un tipo que se va a convertir está fuera del intervalo especificado por el tipo de destino `MaxValue` y `MinValue` campos y la conversión se comprueba el tiempo de ejecución para asegurarse de que el valor de destino tipo no supere su `MaxValue` o `MinValue`.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-131">However, an <xref:System.OverflowException> is thrown if the value of a type that is being converted falls outside of the range specified by the target type's `MaxValue` and `MinValue` fields, and the conversion is checked by the runtime to ensure that the value of the target type does not exceed its `MaxValue` or `MinValue`.</span></span> <span data-ttu-id="d6dc8-132">Las conversiones que se realizan con la <xref:System.Convert?displayProperty=nameWithType> clase siempre se protegen de esta manera.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-132">Conversions that are performed with the <xref:System.Convert?displayProperty=nameWithType> class are always checked in this manner.</span></span>  
  
 <span data-ttu-id="d6dc8-133">En la tabla siguiente se enumera las conversiones que inician una <xref:System.OverflowException> con <xref:System.Convert?displayProperty=nameWithType> o cualquier comprobada conversión si el valor del tipo que se va a convertir está fuera del intervalo definido del tipo resultante.</span><span class="sxs-lookup"><span data-stu-id="d6dc8-133">The following table lists conversions that throw an <xref:System.OverflowException> using <xref:System.Convert?displayProperty=nameWithType> or any checked conversion if the value of the type being converted is outside the defined range of the resulting type.</span></span>  
  
|<span data-ttu-id="d6dc8-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="d6dc8-134">Type</span></span>|<span data-ttu-id="d6dc8-135">Se puede convertir a</span><span class="sxs-lookup"><span data-stu-id="d6dc8-135">Can be converted to</span></span>|  
|----------|-------------------------|  
|<xref:System.Byte>|<xref:System.SByte>|  
|<xref:System.SByte>|<span data-ttu-id="d6dc8-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="d6dc8-136"><xref:System.Byte>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64></span></span>|  
|<xref:System.Int16>|<span data-ttu-id="d6dc8-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="d6dc8-137"><xref:System.Byte>, <xref:System.SByte>, <xref:System.UInt16></span></span>|  
|<xref:System.UInt16>|<span data-ttu-id="d6dc8-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="d6dc8-138"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16></span></span>|  
|<xref:System.Int32>|<span data-ttu-id="d6dc8-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="d6dc8-139"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>,<xref:System.UInt32></span></span>|  
|<xref:System.UInt32>|<span data-ttu-id="d6dc8-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="d6dc8-140"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32></span></span>|  
|<xref:System.Int64>|<span data-ttu-id="d6dc8-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="d6dc8-141"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>,<xref:System.UInt32>,<xref:System.UInt64></span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="d6dc8-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="d6dc8-142"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64></span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="d6dc8-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="d6dc8-143"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Single>|<span data-ttu-id="d6dc8-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="d6dc8-144"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
|<xref:System.Double>|<span data-ttu-id="d6dc8-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="d6dc8-145"><xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.UInt16>, <xref:System.Int32>, <xref:System.UInt32>, <xref:System.Int64>, <xref:System.UInt64></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6dc8-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6dc8-146">See Also</span></span>  
 <xref:System.Convert?displayProperty=nameWithType>  
 [<span data-ttu-id="d6dc8-147">Conversión de tipos en .NET</span><span class="sxs-lookup"><span data-stu-id="d6dc8-147">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
