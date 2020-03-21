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
# <a name="formatfromrawvalue-function"></a>Función FormatFromRawValue
Convierte un valor de datos de rendimiento sin procesar al formato especificado, o bien dos valores de datos de rendimiento sin procesar si la conversión de formato es de duración definida.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

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

## <a name="parameters"></a>Parámetros

`dwCounterType`\
[en] El tipo de contador. Para obtener una lista de tipos de contador, vea Tipos de contador de [rendimiento de WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType`puede ser cualquier tipo `PERF_LARGE_RAW_FRACTION` `PERF_LARGE_RAW_BASE`de contador excepto para y .

`dwFormat`\
[en] Formato al que se convertirán los datos de rendimiento sin procesar. Puede ser uno de los siguientes valores:

|Constante  |Value  |Descripción |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Devuelve el valor calculado como un valor de punto flotante de doble precisión. |
| `PDH_FMT_LARGE` | 0x00000400 | Devuelve el valor calculado como un entero de 64 bits. |
| `PDH_FMT_LONG` | 0x00000100 | Devuelve el valor calculado como un entero de 32 bits. |

Uno de los valores anteriores puede ser ORed con uno de los siguientes indicadores de escalado:

|Constante  |Value  |Descripción |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | No aplique los factores de escala del contador. |
| `PDH_FMT_1000` | 0x00002000 | Multiplique el valor final por 1.000. |

`pTimeBase`\
[en] Un puntero a la base de tiempo, si es necesario para la conversión de formato. Si la información de base de tiempo no es necesaria para la conversión de formato, se omite el valor de este parámetro.

`pRawValue1`\
[en] Puntero a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una estructura que representa un valor de rendimiento sin procesar.

`pRawValue2`\
[en] Puntero a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una estructura que representa un segundo valor de rendimiento sin procesar. Si no es necesario un segundo valor `null`de rendimiento sin procesar, este parámetro debe ser .

`pFmtValue`\
[fuera] Puntero a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) una estructura que recibe el valor de rendimiento con formato.

## <a name="return-value"></a>Valor devuelto

Esta función devuelve los siguientes valores:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La llamada de función es correcta. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Falta un argumento necesario o es incorrecto. |
| `PDH_INVALID_HANDLE` | 0xC0000BBC | El identificador no es un objeto PDH válido. |

## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) función.

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Biblioteca:** PerfCounter.dll

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
