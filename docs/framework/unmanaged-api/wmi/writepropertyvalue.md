---
title: Función WritePropertyValue (referencia de API no administrada)
description: La función WritePropertyValue escribe bytes en una propiedad.
ms.date: 11/06/2017
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
ms.openlocfilehash: a98103367f497b18f9b8fbd61a37abf9816b8356
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107944"
---
# <a name="writepropertyvalue-function"></a>Función WritePropertyValue
Escribe un número específico de bytes en una propiedad identificada por un controlador de propiedad.

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
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instancia.

`lHandle`  
[in] Un entero que contiene el identificador que identifica esta propiedad. El identificador se puede recuperar mediante una llamada a la [GetPropertyHandle](getpropertyhandle.md) función.   

`lNumBytes`  
[in] El número de bytes que se va a escribir en la propiedad. Consulte la [comentarios](#remarks) sección para obtener más información.

`pHandle`   
[out] Un puntero a la matriz de bytes que contiene los datos.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Se ha producido un error de coincidencia de tipo. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) método.

Use esta función para establecer la cadena y todos los otros que no sean de`DWORD` o que no sean-`QWORD` datos.

Para los valores de propiedad, `lNumBytes` debe ser el tamaño de datos correcto del tipo de propiedad especificado. Para los valores de propiedad de cadena, `lNumBytes` debe ser la longitud de la cadena especificada en bytes y la cadena debe tener una longitud en bytes incluso y seguir con un carácter de terminación null.

## <a name="requirements"></a>Requisitos  
**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
