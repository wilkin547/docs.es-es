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
ms.openlocfilehash: e7f3e4eef4a7e378529c2097a8fe1a753a98c961
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553719"
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
de El tipo de contador. Para obtener una lista de tipos de contadores, vea [tipos de contadores de rendimiento de WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType` puede ser cualquier tipo de contador excepto `PERF_LARGE_RAW_FRACTION` y `PERF_LARGE_RAW_BASE` .

`dwFormat`\
de Formato al que se van a convertir los datos de rendimiento sin procesar. Puede ser uno de los siguientes valores:

|Constante  |Valor  |Descripción |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Devuelve el valor calculado como un valor de punto flotante de precisión doble. |
| `PDH_FMT_LARGE` | 0x00000400 | Devuelve el valor calculado como un entero de 64 bits. |
| `PDH_FMT_LONG` | 0x00000100 | Devuelve el valor calculado como un entero de 32 bits. |

Uno de los valores anteriores puede ser ORed con una de las siguientes marcas de escalado:

|Constante  |Valor  |Descripción |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | No aplique los factores de escala del contador. |
| `PDH_FMT_1000` | 0x00002000 | Multiplique el valor final por 1.000. |

`pTimeBase`\
de Puntero a la base de tiempo, si es necesario para la conversión de formato. Si la información de base de tiempo no es necesaria para la conversión de formato, se omite el valor de este parámetro.

`pRawValue1`\
de Puntero a una [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) estructura que representa un valor de rendimiento sin procesar.

`pRawValue2`\
de Puntero a una [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) estructura que representa un segundo valor de rendimiento sin procesar. Si no es necesario un segundo valor de rendimiento sin procesar, este parámetro debe ser `null` .

`pFmtValue`\
enuncia Puntero a una [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) estructura que recibe el valor de rendimiento con formato.

## <a name="return-value"></a>Valor devuelto

Esta función devuelve los valores siguientes:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La llamada de función se realiza correctamente. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Falta un argumento necesario o es incorrecto. |
| `PDH_INVALID_HANDLE` | 0xC0000BBC | El identificador no es un objeto PDH válido. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la función [FormatFromRawValue](/previous-versions/ms231047(v=vs.85)) .

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Biblioteca:** PerfCounter.dll

 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
