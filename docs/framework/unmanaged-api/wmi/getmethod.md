---
title: GetMethod (función) (referencia de API no administrada)
description: La función GetMethod recupera información sobre un método.
ms.date: 11/06/2017
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
ms.openlocfilehash: 133e056663b208f2a0d12f05f31daaca95676dc5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152323"
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
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`wszName`  
[in] El nombre del método. Este parámetro no puede ser `null` y debe apuntar a una `LPCWSTR`.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`ppInSignature`   
[out] Un puntero a la dirección de un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia que describe el paramteers in al método. Este parámetro se omite si se establece en `null`. 

`ppOutSignature`  
[out] Un puntero a la dirección de un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia que se describe los parámetros out del método. Este parámetro se omite si se establece en `null`. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró la propiedad especificada. |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) método.

Administración de Windows se puede establecer el [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntero a `null` si el método no tiene ningún parámetro in.

En `ppInSignature` y `ppOutSignature` describen los parámetros, in y out, respectivamente, como propiedades en un `IWbemClassObject` instancia de la clase del sistema [_Parameters](/windows/desktop/WmiSdk/--parameters). Las propiedades de `ppInsignature` se denominan `Param` *n*, donde *n* es la posición del parámetro en la firma del método (como `Param1`, `Param2`, etcetera.). Las propiedades de `ppOutSignature` también se denominan `Param` *n*, y el valor devuelto se denomina `ReturnValue`. Para obtener más información y un ejemplo, vea [IWbemClassObject::GetMethod método](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).

## <a name="requirements"></a>Requisitos  
**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
