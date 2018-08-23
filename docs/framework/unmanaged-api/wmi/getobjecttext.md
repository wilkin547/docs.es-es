---
title: GetObjectText (función) (referencia de API no administrada)
description: GetObjectText (función), devuelve una representación textual de un objeto en la sintaxis MOF.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24ba4b37cc8221df4e018d172996c0910ec07f7d
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754442"
---
# <a name="getobjecttext-function"></a>GetObjectText (función)
Devuelve una representación textual del objeto en la sintaxis de Managed Object Format (MOF).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`lFlags`  
[in] Normalmente 0. Si `WBEM_FLAG_NO_FLAVORS` (o 0 x 1) se especifica, se incluyen sin información de propagación o flavor calificadores.

`pstrObjectText`   
[out] Un puntero a un `null` en la entrada. Devuelve un recién asignado `BSTR` que contiene una representación de la sintaxis MOF del objeto.  

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | Ha habido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) método.

Devuelve el texto MOF contiene toda la información sobre el objeto, sino únicamente la información suficiente para que el compilador MOF poder volver a crear el objeto original. Por ejemplo, no propagados calificadores o propiedades de la clase primaria se incluyen.

El siguiente algoritmo se utiliza para reconstruir el texto de los parámetros de un método:

1. Se cambia la secuencia de parámetros en el orden de sus valores de identificador.
1. Los parámetros que se especifican como `[in]` y `[out]` se combinan en un único parámetro.
 
`pstrObjectText` debe ser un puntero a un `null` cuando se llama a la función; no debe apuntar a una cadena que es válida antes de la llamada de método, porque no se cancelará el puntero.

## <a name="requirements"></a>Requisitos  
**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
