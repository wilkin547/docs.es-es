---
title: GetMethod (función) (referencia de la API no administrada)
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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102590"
---
# <a name="getmethod-function"></a>Función GetMethod

Recupera información sobre el método especificado.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
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

`vFunc`\
de Este parámetro no se utiliza.

`ptr`\
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
de Nombre del método. Este parámetro no se puede `null` y debe apuntar a un `LPCWSTR`válido.

`lFlags`\
[in] Reservado. Este parámetro debe ser 0.

`ppInSignature`\
enuncia Puntero a la dirección de una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que describe los parámetros in para el método. Se omite este parámetro si se establece en `null`.

`ppOutSignature`\
enuncia Puntero a la dirección de una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que describe los parámetros out para el método. Se omite este parámetro si se establece en `null`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró la propiedad especificada. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .

La administración de Windows puede establecer el puntero [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) en `null` si el método no tiene parámetros in.

En `ppInSignature` y `ppOutSignature` describen los parámetros in y out, respectivamente, como propiedades en una instancia de `IWbemClassObject` de la clase del sistema [_Parameters](/windows/desktop/WmiSdk/--parameters). Las propiedades de `ppInSignature` se denominan `Param`*n*, donde *n* es la posición del parámetro en la firma del método (como `Param1`, `Param2`, etc.). Las propiedades de `ppOutSignature` también se denominan `Param`*n*y el valor devuelto se llama `ReturnValue`. Para obtener más información y un ejemplo, vea el [método IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** WMINet_Utils. idl

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
