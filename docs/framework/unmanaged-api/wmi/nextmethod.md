---
title: Función NextMethod (referencia de la API no administrada)
description: La función NextMethod recupera el método siguiente en una enumeración.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1c20fe5b4a081bd41f51365a36ab5f8f8cfb71ed
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127358"
---
# <a name="nextmethod-function"></a>NextMethod función)
Recupera el método siguiente en una enumeración que comienza con una llamada a [BeginMethodEnumeration](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pName`  
enuncia Puntero que apunta a `null` antes de la llamada. Cuando la función devuelve, la dirección de un nuevo `BSTR` que contiene el nombre del método. 

`ppSignatureIn`  
enuncia Puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene los parámetros de `in` para el método. 

`ppSignatureOut`  
enuncia Puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene los parámetros de `out` para el método. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | No había ninguna llamada a la función [`BeginEnumeration`](beginenumeration.md) . |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No hay más propiedades en la enumeración. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

El autor de la llamada comienza la secuencia de enumeración mediante una llamada a la función [BeginMethodEnumeration](beginmethodenumeration.md) y, a continuación, llama a la función [NextMethod] hasta que la función devuelve `WBEM_S_NO_MORE_DATA`. Opcionalmente, el autor de la llamada finaliza la secuencia llamando a [EndMethodEnumeration](endmethodenumeration.md). El autor de la llamada puede finalizar la enumeración pronto llamando a [EndMethodEnumeration](endmethodenumeration.md) en cualquier momento.

## <a name="example"></a>Ejemplo

Para obtener C++ un ejemplo, vea el método [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
