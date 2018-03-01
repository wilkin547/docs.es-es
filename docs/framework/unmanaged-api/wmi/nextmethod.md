---
title: "Función NextMethod (referencia de API no administrada)"
description: "La función NextMethod recupera el método siguiente en una enumeración."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b886b3ecbd1d5b5b8d212846b2bd8291fa43909
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="nextmethod-function"></a>NextMethod (función)
Recupera el siguiente método de enumeración que comienza con una llamada a [BeginMethodEnumeration](beginmethodenumeration.md).  

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
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`lFlags`  
[in] Reservado. Este parámetro debe ser 0.

`pName`  
[out] Un puntero que señala a `null` antes de la llamada. Cuando se devuelve la función, la dirección de un nuevo `BSTR` que contiene el nombre del método. 

`ppSignatureIn`  
[out] Un puntero que recibe un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) que contiene el `in` parámetros para el método. 

`ppSignatureOut`  
[out] Un puntero que recibe un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) que contiene el `out` parámetros para el método. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Se ha producido ninguna llamada a la [ `BeginEnumeration` ](beginenumeration.md) (función). |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No hay ninguna propiedad más en la enumeración. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) método.

El llamador inicia la secuencia de enumeración mediante una llamada a la [BeginMethodEnumeration](beginmethodenumeration.md) función y, a continuación, llama a la función [NextMethod] hasta que regresa la función `WBEM_S_NO_MORE_DATA`. Si lo desea, el llamador finaliza la secuencia mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md). El llamador puede finalizar la enumeración al principio mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md) en cualquier momento.

## <a name="example"></a>Ejemplo

Para obtener un ejemplo de C++, vea la [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
