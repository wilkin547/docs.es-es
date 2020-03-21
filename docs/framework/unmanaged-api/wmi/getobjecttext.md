---
title: Función GetObjectText (Referencia de API no administrada)
description: La función GetObjectText devuelve una representación textual de un objeto en sintaxis MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176791"
---
# <a name="getobjecttext-function"></a>Función GetObjectText
Devuelve una representación textual del objeto en la sintaxis de formato de objeto administrado (MOF).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[en] Este parámetro no se utiliza.

`ptr`  
[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[en] Normalmente 0. Si `WBEM_FLAG_NO_FLAVORS` se especifica (o 0x1), los calificadores se incluyen sin información de propagación o sabor.

`pstrObjectText`[fuera] Un puntero `null` a una entrada on. A la vuelta, `BSTR` un recién asignado que contiene una representación de sintaxis MOF del objeto.  

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Ha habido un fracaso general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insuficiente para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) método.

El texto MOF devuelto no contiene toda la información sobre el objeto, sino solo suficiente información para que el compilador MOF pueda volver a crear el objeto original. Por ejemplo, no se incluyen calificadores propagados ni propiedades de clase primaria.

El siguiente algoritmo se utiliza para reconstruir el texto de los parámetros de un método:

1. Los parámetros se vuelven a secuenciar en el orden de sus valores de identificador.
1. Parámetros que se `[in]` `[out]` especifican como y se combinan en un único parámetro.

`pstrObjectText`debe ser un `null` puntero a un cuando se llama a la función; no debe apuntar a una cadena que sea válida antes de la llamada al método, porque el puntero no se desasignará.

## <a name="requirements"></a>Requisitos  
**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
