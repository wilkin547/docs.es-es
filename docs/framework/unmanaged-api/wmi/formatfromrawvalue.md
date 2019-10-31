---
title: Función FormatFromRawValue (referencia de la API no administrada)
description: La función FormatFromRawValue convierte los datos de rendimiento sin procesar en un formato especificado.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5097cfe43ae785461a1e2af1217bcbd5e8c4b79c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120286"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="dcc42-103">Función FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="dcc42-103">FormatFromRawValue function</span></span>
<span data-ttu-id="dcc42-104">Convierte un valor de datos de rendimiento sin procesar al formato especificado, o bien dos valores de datos de rendimiento sin procesar si la conversión de formato es de duración definida.</span><span class="sxs-lookup"><span data-stu-id="dcc42-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="dcc42-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dcc42-105">Syntax</span></span>

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```

## <a name="parameters"></a><span data-ttu-id="dcc42-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dcc42-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="dcc42-107">de El tipo de contador.</span><span class="sxs-lookup"><span data-stu-id="dcc42-107">[in] The counter type.</span></span> <span data-ttu-id="dcc42-108">Para obtener una lista de tipos de contadores, vea [tipos de contadores de rendimiento de WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="dcc42-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="dcc42-109">`dwCounterType` puede ser cualquier tipo de contador excepto `PERF_LARGE_RAW_FRACTION` y `PERF_LARGE_RAW_BASE`.</span><span class="sxs-lookup"><span data-stu-id="dcc42-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`\
<span data-ttu-id="dcc42-110">de Formato al que se van a convertir los datos de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="dcc42-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="dcc42-111">Puede ser uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="dcc42-111">It can be one of the following values:</span></span>

|<span data-ttu-id="dcc42-112">Constante</span><span class="sxs-lookup"><span data-stu-id="dcc42-112">Constant</span></span>  |<span data-ttu-id="dcc42-113">Valor</span><span class="sxs-lookup"><span data-stu-id="dcc42-113">Value</span></span>  |<span data-ttu-id="dcc42-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcc42-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="dcc42-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="dcc42-115">0x00000200</span></span> | <span data-ttu-id="dcc42-116">Devuelve el valor calculado como un valor de punto flotante de precisión doble.</span><span class="sxs-lookup"><span data-stu-id="dcc42-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="dcc42-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="dcc42-117">0x00000400</span></span> | <span data-ttu-id="dcc42-118">Devuelve el valor calculado como un entero de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="dcc42-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="dcc42-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="dcc42-119">0x00000100</span></span> | <span data-ttu-id="dcc42-120">Devuelve el valor calculado como un entero de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="dcc42-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="dcc42-121">Uno de los valores anteriores puede ser ORed con una de las siguientes marcas de escalado:</span><span class="sxs-lookup"><span data-stu-id="dcc42-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="dcc42-122">Constante</span><span class="sxs-lookup"><span data-stu-id="dcc42-122">Constant</span></span>  |<span data-ttu-id="dcc42-123">Valor</span><span class="sxs-lookup"><span data-stu-id="dcc42-123">Value</span></span>  |<span data-ttu-id="dcc42-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcc42-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="dcc42-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="dcc42-125">0x00001000</span></span> | <span data-ttu-id="dcc42-126">No aplique los factores de escala del contador.</span><span class="sxs-lookup"><span data-stu-id="dcc42-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="dcc42-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="dcc42-127">0x00002000</span></span> | <span data-ttu-id="dcc42-128">Multiplique el valor final por 1.000.</span><span class="sxs-lookup"><span data-stu-id="dcc42-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`\
<span data-ttu-id="dcc42-129">de Puntero a la base de tiempo, si es necesario para la conversión de formato.</span><span class="sxs-lookup"><span data-stu-id="dcc42-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="dcc42-130">Si la información de base de tiempo no es necesaria para la conversión de formato, se omite el valor de este parámetro.</span><span class="sxs-lookup"><span data-stu-id="dcc42-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="dcc42-131">`pRawValue1`\ [in] un puntero a una estructura de [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) que representa un valor de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="dcc42-131">`pRawValue1`\ [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="dcc42-132">de Puntero a una estructura de [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) que representa un segundo valor de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="dcc42-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="dcc42-133">Si no es necesario un segundo valor de rendimiento sin procesar, este parámetro se debe `null`.</span><span class="sxs-lookup"><span data-stu-id="dcc42-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="dcc42-134">enuncia Puntero a una estructura de [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) que recibe el valor de rendimiento con formato.</span><span class="sxs-lookup"><span data-stu-id="dcc42-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="dcc42-135">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dcc42-135">Return value</span></span>

<span data-ttu-id="dcc42-136">Esta función devuelve los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcc42-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="dcc42-137">Constante</span><span class="sxs-lookup"><span data-stu-id="dcc42-137">Constant</span></span>  |<span data-ttu-id="dcc42-138">Valor</span><span class="sxs-lookup"><span data-stu-id="dcc42-138">Value</span></span>  |<span data-ttu-id="dcc42-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcc42-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="dcc42-140">0</span><span class="sxs-lookup"><span data-stu-id="dcc42-140">0</span></span> | <span data-ttu-id="dcc42-141">La llamada de función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="dcc42-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="dcc42-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="dcc42-142">0xC0000BBD</span></span> | <span data-ttu-id="dcc42-143">Falta un argumento necesario o es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="dcc42-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="dcc42-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="dcc42-144">0xC0000BBC</span></span> | <span data-ttu-id="dcc42-145">El identificador no es un objeto PDH válido.</span><span class="sxs-lookup"><span data-stu-id="dcc42-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="dcc42-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dcc42-146">Remarks</span></span>

<span data-ttu-id="dcc42-147">Esta función contiene una llamada a la función [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) .</span><span class="sxs-lookup"><span data-stu-id="dcc42-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="dcc42-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcc42-148">Requirements</span></span>

 <span data-ttu-id="dcc42-149">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcc42-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="dcc42-150">**Biblioteca:** PerfCounter. dll</span><span class="sxs-lookup"><span data-stu-id="dcc42-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="dcc42-151">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc42-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dcc42-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcc42-152">See also</span></span>

- [<span data-ttu-id="dcc42-153">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="dcc42-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
