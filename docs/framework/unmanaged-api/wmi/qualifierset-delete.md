---
title: "Función QualifierSet_Delete (referencia de API no administrada)"
description: "La función QualifierSet_Delete elimina un calificador por su nombre."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e7b5650a0b47fd8d9b64bb9d0fff3511afe2d43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetdelete-function"></a>QualifierSet_Delete (función)
Elimina un calificador especificado por su nombre.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.

`wszName`   
[in] El nombre del calificador para eliminar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | El `wszName` parámetro no es válido. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Eliminar este calificador no es válido. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró el calificador especificado. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Se ha eliminado la invalidación local y el calificador del objeto primario original ha reanudado el ámbito. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) método.

Debido a las reglas de propagación de calificador, un calificador determinado puede haberse se hereda de otro objeto y simplemente se reemplaza en la clase actual o la instancia. En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor original heredado. En este caso, la función devuelve el código de estado `WBEM_S_RESET_TO_DEFAULT`.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
