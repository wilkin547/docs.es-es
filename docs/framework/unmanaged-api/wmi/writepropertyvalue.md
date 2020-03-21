---
title: Función WritePropertyValue (Referencia de API no administrada)
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174841"
---
# <a name="writepropertyvalue-function"></a>Función WritePropertyValue
Escribe un número específico de bytes en una propiedad identificada por un controlador de propiedad.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
[en] Este parámetro no se utiliza.

`ptr`  
[en] Puntero a una instancia de [IWbemObjectAccess.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)

`lHandle`  
[en] Entero que contiene el identificador que identifica esta propiedad. El identificador se puede recuperar mediante una llamada a la [GetPropertyHandle](getpropertyhandle.md) función.

`lNumBytes`  
[en] El número de bytes que se escriben en la propiedad. Consulte la sección [Comentarios](#remarks) para obtener más información.

`pHandle`[fuera] Puntero a la matriz de bytes que contiene los datos.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Se produjo un desajuste de tipos. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) método.

Utilice esta función para establecer`DWORD` la cadena`QWORD` y todos los demás datos no o no.

Para los valores `lNumBytes` de propiedad que no son de cadena, debe ser el tamaño de datos correcto del tipo de propiedad especificado. Para los valores `lNumBytes` de propiedad de cadena, debe ser la longitud de la cadena especificada en bytes y la cadena en sí debe tener una longitud par en bytes y seguirse con un carácter de terminación nula.

## <a name="requirements"></a>Requisitos  
**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
