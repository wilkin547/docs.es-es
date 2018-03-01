---
title: "Función WritePropertyValue (referencia de API no administrada)"
description: "La función WritePropertyValue escribe bytes a una propiedad."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7221c9e0f1cb49ab0e27130ce69c0527ba903148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue (función)
Escribe un número especificado de bytes en una propiedad identificada por un identificador de propiedad.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instancia.

`lHandle`  
[in] Un entero que contiene el identificador que identifica esta propiedad. El identificador se puede recuperar mediante una llamada a la [GetPropertyHandle](getpropertyhandle.md) (función).   

`lNumBytes`  
[in] El número de bytes que se va a escribir en la propiedad. Consulte la [comentarios](#remarks) sección para obtener más información.

`pHandle`   
[out] Un puntero a la matriz de bytes que contiene los datos.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
|`WBEM_E_TYPE_MISMATCH` | 0 x 80041005 | Se produjo un error de coincidencia de tipo. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) método.

Use esta función para establecer la cadena y todos los demás no -`DWORD` o no-`QWORD` datos.

Para los valores de propiedad que no son cadenas, `lNumBytes` debe ser el tamaño de los datos correctos del tipo de propiedad especificado. Para los valores de propiedad de cadena, `lNumBytes` deben tener la longitud de la cadena especificada en bytes y la cadena debe ser de un par de longitud en bytes e ir seguida de un carácter de terminación null.

## <a name="requirements"></a>Requisitos  
**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
