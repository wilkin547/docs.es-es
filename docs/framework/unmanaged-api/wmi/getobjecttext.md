---
title: Función GetObjectText (referencia de la API no administrada)
description: La función GetObjectText devuelve una representación textual de un objeto en la sintaxis MOF.
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
ms.openlocfilehash: 6ad2b29202222d594cc7976a13929002164314a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718376"
---
# <a name="getobjecttext-function"></a>Función GetObjectText

Devuelve una representación textual del objeto en la sintaxis de Managed Object Format (MOF).

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
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
de Normalmente 0. Si `WBEM_FLAG_NO_FLAVORS` se especifica (o 0x1), los calificadores se incluyen sin información de propagación o de tipo.

`pstrObjectText` enuncia Puntero a una `null` entrada. En la devolución, una recién asignada `BSTR` que contiene una representación de la sintaxis MOF del objeto.  

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insuficiente para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .

El texto MOF devuelto no contiene toda la información sobre el objeto, sino solo información suficiente para que el compilador MOF pueda volver a crear el objeto original. Por ejemplo, no se incluye ningún calificador propagado ni propiedades de clase primaria.

El algoritmo siguiente se usa para reconstruir el texto de los parámetros de un método:

1. Los parámetros se reordenan en el orden de sus valores de identificador.
1. Los parámetros que se especifican como `[in]` y `[out]` se combinan en un único parámetro.

`pstrObjectText` debe ser un puntero a `null` cuando se llama a la función; no debe apuntar a una cadena que sea válida antes de la llamada al método, ya que el puntero no se desasignará.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
