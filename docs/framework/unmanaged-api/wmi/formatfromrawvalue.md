---
title: Función FormatFromRawValue (Referencia de API no administrada)
description: La función FormatFromRawValue convierte los datos de rendimiento sin procesar a un formato especificado.
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
ms.openlocfilehash: 0a7c0b8387f0c8e2b6e2ade94f7efeede75bd758
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176843"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="4e710-103">Función FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="4e710-103">FormatFromRawValue function</span></span>
<span data-ttu-id="4e710-104">Convierte un valor de datos de rendimiento sin procesar al formato especificado, o bien dos valores de datos de rendimiento sin procesar si la conversión de formato es de duración definida.</span><span class="sxs-lookup"><span data-stu-id="4e710-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4e710-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e710-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="4e710-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e710-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="4e710-107">[en] El tipo de contador.</span><span class="sxs-lookup"><span data-stu-id="4e710-107">[in] The counter type.</span></span> <span data-ttu-id="4e710-108">Para obtener una lista de tipos de contador, vea Tipos de contador de [rendimiento de WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="4e710-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="4e710-109">`dwCounterType`puede ser cualquier tipo `PERF_LARGE_RAW_FRACTION` `PERF_LARGE_RAW_BASE`de contador excepto para y .</span><span class="sxs-lookup"><span data-stu-id="4e710-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="4e710-110">[en] Formato al que se convertirán los datos de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="4e710-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="4e710-111">Puede ser uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4e710-111">It can be one of the following values:</span></span>

|<span data-ttu-id="4e710-112">Constante</span><span class="sxs-lookup"><span data-stu-id="4e710-112">Constant</span></span>  |<span data-ttu-id="4e710-113">Value</span><span class="sxs-lookup"><span data-stu-id="4e710-113">Value</span></span>  |<span data-ttu-id="4e710-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e710-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="4e710-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="4e710-115">0x00000200</span></span> | <span data-ttu-id="4e710-116">Devuelve el valor calculado como un valor de punto flotante de doble precisión.</span><span class="sxs-lookup"><span data-stu-id="4e710-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="4e710-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="4e710-117">0x00000400</span></span> | <span data-ttu-id="4e710-118">Devuelve el valor calculado como un entero de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4e710-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="4e710-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="4e710-119">0x00000100</span></span> | <span data-ttu-id="4e710-120">Devuelve el valor calculado como un entero de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4e710-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="4e710-121">Uno de los valores anteriores puede ser ORed con uno de los siguientes indicadores de escalado:</span><span class="sxs-lookup"><span data-stu-id="4e710-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="4e710-122">Constante</span><span class="sxs-lookup"><span data-stu-id="4e710-122">Constant</span></span>  |<span data-ttu-id="4e710-123">Value</span><span class="sxs-lookup"><span data-stu-id="4e710-123">Value</span></span>  |<span data-ttu-id="4e710-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e710-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="4e710-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="4e710-125">0x00001000</span></span> | <span data-ttu-id="4e710-126">No aplique los factores de escala del contador.</span><span class="sxs-lookup"><span data-stu-id="4e710-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="4e710-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="4e710-127">0x00002000</span></span> | <span data-ttu-id="4e710-128">Multiplique el valor final por 1.000.</span><span class="sxs-lookup"><span data-stu-id="4e710-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="4e710-129">[en] Un puntero a la base de tiempo, si es necesario para la conversión de formato.</span><span class="sxs-lookup"><span data-stu-id="4e710-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="4e710-130">Si la información de base de tiempo no es necesaria para la conversión de formato, se omite el valor de este parámetro.</span><span class="sxs-lookup"><span data-stu-id="4e710-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="4e710-131">[en] Puntero a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una estructura que representa un valor de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="4e710-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="4e710-132">[en] Puntero a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una estructura que representa un segundo valor de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="4e710-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="4e710-133">Si no es necesario un segundo valor `null`de rendimiento sin procesar, este parámetro debe ser .</span><span class="sxs-lookup"><span data-stu-id="4e710-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="4e710-134">[fuera] Puntero a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) una estructura que recibe el valor de rendimiento con formato.</span><span class="sxs-lookup"><span data-stu-id="4e710-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="4e710-135">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e710-135">Return value</span></span>

<span data-ttu-id="4e710-136">Esta función devuelve los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4e710-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="4e710-137">Constante</span><span class="sxs-lookup"><span data-stu-id="4e710-137">Constant</span></span>  |<span data-ttu-id="4e710-138">Value</span><span class="sxs-lookup"><span data-stu-id="4e710-138">Value</span></span>  |<span data-ttu-id="4e710-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e710-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="4e710-140">0</span><span class="sxs-lookup"><span data-stu-id="4e710-140">0</span></span> | <span data-ttu-id="4e710-141">La llamada de función es correcta.</span><span class="sxs-lookup"><span data-stu-id="4e710-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="4e710-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="4e710-142">0xC0000BBD</span></span> | <span data-ttu-id="4e710-143">Falta un argumento necesario o es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="4e710-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="4e710-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="4e710-144">0xC0000BBC</span></span> | <span data-ttu-id="4e710-145">El identificador no es un objeto PDH válido.</span><span class="sxs-lookup"><span data-stu-id="4e710-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="4e710-146">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4e710-146">Remarks</span></span>

<span data-ttu-id="4e710-147">Esta función ajusta una llamada a la [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) función.</span><span class="sxs-lookup"><span data-stu-id="4e710-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e710-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e710-148">Requirements</span></span>

 <span data-ttu-id="4e710-149">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e710-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="4e710-150">**Biblioteca:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="4e710-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="4e710-151">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4e710-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4e710-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e710-152">See also</span></span>

- [<span data-ttu-id="4e710-153">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="4e710-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
