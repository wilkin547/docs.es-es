---
title: "GetMethod (función) (referencia de API no administrada)"
description: "La función GetMethod recupera información sobre un método."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f22a2dfa7aae411cac960cbad2017718df8057e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getmethod-function"></a>GetMethod (función)
Recupera información sobre el método especificado.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`wszName`  
[in] El nombre del método. Este parámetro no puede ser `null` y debe señalar a válido `LPCWSTR`.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppInSignature`   
[out] Un puntero a la dirección de un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia que describe la paramteers en el método. Este parámetro se ignora si se establece en `null`. 

`ppOutSignature`  
[out] Un puntero a la dirección de un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia que describe los parámetros de salida para el método. Este parámetro se ignora si se establece en `null`. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró la propiedad especificada. |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) método.

Administración de Windows se puede establecer la [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) puntero a `null` si el método no tiene ningún parámetro in.

En `ppInSignature` y `ppOutSignature` describen in y out parámetros, respectivamente, como propiedades en un `IWbemClassObject` instancia de la clase del sistema [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx). Las propiedades de `ppInsignature` se denominan **Param***n*, donde  *n*  es la posición del parámetro en la firma del método (por ejemplo, como `Param1`, `Param2`, etcetera.). Las propiedades de `ppOutSignature` también se denominan **Param***n*, y el valor devuelto se denomina **ReturnValue**. Para obtener más información y un ejemplo, vea [IWbemClassObject::GetMethod método](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).

## <a name="requirements"></a>Requisitos  
**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
