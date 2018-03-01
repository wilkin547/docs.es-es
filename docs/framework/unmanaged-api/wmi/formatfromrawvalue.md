---
title: "Función FormatFromRawValue (referencia de API no administrada)"
description: "La función FormatFromRawValue convierte los datos de rendimiento sin procesar a un formato especificado."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3daa89ec0b40bb9c08898ecd682f05f0f0ce09a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue (función)
Convierte un valor de datos de rendimiento sin procesar en el formato especificado, o dos valores de datos de rendimiento sin procesar si la conversión de formato se basa en el tiempo.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
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

## <a name="parameters"></a>Parámetros

`dwCounterType`  
[in] El tipo de contador. Para obtener una lista de tipos de contador, vea [WMI Performance Counter Types](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx). `dwCounterType`puede ser cualquier tipo de contador excepto `PERF_LARGE_RAW_FRACTION` y `PERF_LARGE_RAW_BASE`. 

`dwFormat`  
[in] El formato que se va a convertir los datos de rendimiento sin procesar. Puede ser uno de los siguientes valores:

|Constante  |Valor  |Descripción |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Devuelve el valor calculado como un valor de punto flotante de precisión doble. | 
| `PDH_FMT_LARGE` | 0x00000400 | Devuelve el valor calculado como un entero de 64 bits. |
| `PDH_FMT_LONG` | 0x00000100 | Devuelve el valor calculado como un entero de 32 bits. |

Uno de los valores anteriores puede ser ORed con uno de los siguientes indicadores de escala:

|Constante  |Valor  |Descripción |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | No se aplican los factores de escala del contador. |
| `PDH_FMT_1000` | 0x00002000 | El valor final se multiplica por 1000. | 

`pTimeBase`  
[in] Un puntero a la base de tiempo, si es necesario para la conversión de formato. Si la información de base de tiempo no es necesario para la conversión de formato, se omite el valor de este parámetro.

`pRawValue1`[in] Un puntero a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) estructura que representa un valor de rendimiento sin procesar.

`pRawValue2`[in] Un puntero a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) estructura que representa un segundo valor de rendimiento sin procesar. Si no es necesario un segundo valor de rendimiento sin procesar, este parámetro debe ser `null`.

`pFmtValue`[out] Un puntero a un [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) estructura que recibe el valor de rendimiento con formato.

## <a name="return-value"></a>Valor devuelto

Esta función devuelve los siguientes valores:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La llamada de función es correcta. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Un argumento requerido falta o es incorrecto. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | El identificador no es un objeto PDH válido. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) función.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Biblioteca:** PerfCounter.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
