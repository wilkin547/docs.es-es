---
title: Función NextMethod (referencia de API no administrada)
description: La función NextMethod recupera el siguiente método en una enumeración.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ebe6924dfe1a4aa640ef8ccd7b4047c1d137948
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640048"
---
# <a name="nextmethod-function"></a>Función NextMethod
Recupera el siguiente método en una enumeración que comienza con una llamada a [BeginMethodEnumeration](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pName`  
[out] Un puntero que señala a `null` antes de la llamada. Cuando se devuelve la función, la dirección de un nuevo `BSTR` que contiene el nombre del método. 

`ppSignatureIn`  
[out] Un puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene el `in` parámetros del método. 

`ppSignatureOut`  
[out] Un puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene el `out` parámetros del método. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Se ha producido ninguna llamada a la [ `BeginEnumeration` ](beginenumeration.md) función. |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No hay ninguna propiedad más en la enumeración. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) método.

El llamador inicia la secuencia de enumeración al llamar a la [BeginMethodEnumeration](beginmethodenumeration.md) función y, a continuación, llama a la función [NextMethod] hasta que la función devuelve `WBEM_S_NO_MORE_DATA`. Si lo desea, el llamador finaliza la secuencia mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md). El llamador puede finalizar la enumeración al principio mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md) en cualquier momento.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo de C++, vea el [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también
- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
