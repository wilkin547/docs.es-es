---
title: Función FormatFromRawValue (referencia de API no administrada)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0710b26237b350f1dfbc7d2464b7a131373604e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460426"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="66ec7-103">FormatFromRawValue (función)</span><span class="sxs-lookup"><span data-stu-id="66ec7-103">FormatFromRawValue function</span></span>
<span data-ttu-id="66ec7-104">Convierte un valor de datos de rendimiento sin procesar en el formato especificado, o dos valores de datos de rendimiento sin procesar si la conversión de formato se basa en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="66ec7-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="66ec7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66ec7-105">Syntax</span></span>  
  
```  
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```  

## <a name="parameters"></a><span data-ttu-id="66ec7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66ec7-106">Parameters</span></span>

`dwCounterType`  
<span data-ttu-id="66ec7-107">[in] El tipo de contador.</span><span class="sxs-lookup"><span data-stu-id="66ec7-107">[in] The counter type.</span></span> <span data-ttu-id="66ec7-108">Para obtener una lista de tipos de contador, vea [WMI Performance Counter Types](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="66ec7-108">For a list of counter types, see [WMI Performance Counter Types](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx).</span></span> <span data-ttu-id="66ec7-109">`dwCounterType` puede ser cualquier tipo de contador excepto `PERF_LARGE_RAW_FRACTION` y `PERF_LARGE_RAW_BASE`.</span><span class="sxs-lookup"><span data-stu-id="66ec7-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`  
<span data-ttu-id="66ec7-110">[in] El formato que se va a convertir los datos de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="66ec7-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="66ec7-111">Puede ser uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="66ec7-111">It can be one of the following values:</span></span>

|<span data-ttu-id="66ec7-112">Constante</span><span class="sxs-lookup"><span data-stu-id="66ec7-112">Constant</span></span>  |<span data-ttu-id="66ec7-113">Valor</span><span class="sxs-lookup"><span data-stu-id="66ec7-113">Value</span></span>  |<span data-ttu-id="66ec7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="66ec7-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="66ec7-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="66ec7-115">0x00000200</span></span> | <span data-ttu-id="66ec7-116">Devuelve el valor calculado como un valor de punto flotante de precisión doble.</span><span class="sxs-lookup"><span data-stu-id="66ec7-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="66ec7-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="66ec7-117">0x00000400</span></span> | <span data-ttu-id="66ec7-118">Devuelve el valor calculado como un entero de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="66ec7-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="66ec7-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="66ec7-119">0x00000100</span></span> | <span data-ttu-id="66ec7-120">Devuelve el valor calculado como un entero de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="66ec7-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="66ec7-121">Uno de los valores anteriores puede ser ORed con uno de los siguientes indicadores de escala:</span><span class="sxs-lookup"><span data-stu-id="66ec7-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="66ec7-122">Constante</span><span class="sxs-lookup"><span data-stu-id="66ec7-122">Constant</span></span>  |<span data-ttu-id="66ec7-123">Valor</span><span class="sxs-lookup"><span data-stu-id="66ec7-123">Value</span></span>  |<span data-ttu-id="66ec7-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="66ec7-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="66ec7-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="66ec7-125">0x00001000</span></span> | <span data-ttu-id="66ec7-126">No se aplican los factores de escala del contador.</span><span class="sxs-lookup"><span data-stu-id="66ec7-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="66ec7-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="66ec7-127">0x00002000</span></span> | <span data-ttu-id="66ec7-128">El valor final se multiplica por 1000.</span><span class="sxs-lookup"><span data-stu-id="66ec7-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`  
<span data-ttu-id="66ec7-129">[in] Un puntero a la base de tiempo, si es necesario para la conversión de formato.</span><span class="sxs-lookup"><span data-stu-id="66ec7-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="66ec7-130">Si la información de base de tiempo no es necesario para la conversión de formato, se omite el valor de este parámetro.</span><span class="sxs-lookup"><span data-stu-id="66ec7-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="66ec7-131">`pRawValue1` [in] Un puntero a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) estructura que representa un valor de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="66ec7-131">`pRawValue1` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a raw performance value.</span></span>

<span data-ttu-id="66ec7-132">`pRawValue2` [in] Un puntero a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) estructura que representa un segundo valor de rendimiento sin procesar.</span><span class="sxs-lookup"><span data-stu-id="66ec7-132">`pRawValue2` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a second raw performance value.</span></span> <span data-ttu-id="66ec7-133">Si no es necesario un segundo valor de rendimiento sin procesar, este parámetro debe ser `null`.</span><span class="sxs-lookup"><span data-stu-id="66ec7-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

<span data-ttu-id="66ec7-134">`pFmtValue` [out] Un puntero a un [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) estructura que recibe el valor de rendimiento con formato.</span><span class="sxs-lookup"><span data-stu-id="66ec7-134">`pFmtValue` [out] A pointer to a [`PDH_FMT_COUNTERVALUE`](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="66ec7-135">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="66ec7-135">Return value</span></span>

<span data-ttu-id="66ec7-136">Esta función devuelve los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="66ec7-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="66ec7-137">Constante</span><span class="sxs-lookup"><span data-stu-id="66ec7-137">Constant</span></span>  |<span data-ttu-id="66ec7-138">Valor</span><span class="sxs-lookup"><span data-stu-id="66ec7-138">Value</span></span>  |<span data-ttu-id="66ec7-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="66ec7-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="66ec7-140">0</span><span class="sxs-lookup"><span data-stu-id="66ec7-140">0</span></span> | <span data-ttu-id="66ec7-141">La llamada de función es correcta.</span><span class="sxs-lookup"><span data-stu-id="66ec7-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="66ec7-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="66ec7-142">0xC0000BBD</span></span> | <span data-ttu-id="66ec7-143">Un argumento requerido falta o es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="66ec7-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="66ec7-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="66ec7-144">0xC0000BBC</span></span> | <span data-ttu-id="66ec7-145">El identificador no es un objeto PDH válido.</span><span class="sxs-lookup"><span data-stu-id="66ec7-145">The handle is not a valid PDH object.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="66ec7-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66ec7-146">Remarks</span></span>

<span data-ttu-id="66ec7-147">Esta función contiene una llamada a la [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) función.</span><span class="sxs-lookup"><span data-stu-id="66ec7-147">This function wraps a call to the [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="66ec7-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66ec7-148">Requirements</span></span>  
 <span data-ttu-id="66ec7-149">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66ec7-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66ec7-150">**Biblioteca:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="66ec7-150">**Library:** PerfCounter.dll</span></span>  
  
 <span data-ttu-id="66ec7-151">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="66ec7-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ec7-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="66ec7-152">See also</span></span>  
[<span data-ttu-id="66ec7-153">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="66ec7-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
