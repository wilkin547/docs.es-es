---
title: "Eliminar función (referencia de API no administrada)"
description: "La función de eliminación elimina la propiedad especificada y todas sus calificadores de una definición de clase CIM."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30f5bf651990cafe06811019cf2b3d92f866f646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="delete-function"></a>Eliminar (función)
Elimina la propiedad especificada y todas sus calificadores de una definición de clase CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`wszName`  
[in] El nombre de la propiedad que se va a eliminar. `wszName`debe ser un puntero a un válido `LPCWSTR`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | No se puede eliminar la propiedad. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | `wszzName` no es válido. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La propiedad especificada no existe. |
| `WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay memoria suficiente para completar la operación. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | La propiedad se hereda de una clase base. |
| `WBEM_E_SYSTEM_PROPERTY` | | La propiedad es una propiedad del sistema. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | La función elimina un valor de invalidación predeterminado para la clase actual. El valor predeterminado de esta propiedad en la clase primaria ha sido reactiviated. | 

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
