---
title: Función QualifierSet_Delete (referencia de API no administrada)
description: La función QualifierSet_Delete elimina un calificador por su nombre.
ms.date: 11/06/2017
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
ms.openlocfilehash: 7ca4cc9fb65d1a4bd8713f969bbda5551ce5a2e2
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929787"
---
# <a name="qualifiersetdelete-function"></a>Función QualifierSet_Delete
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
[in] Este parámetro se usa.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.

`wszName`   
[in] El nombre del calificador que se va a eliminar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | El `wszName` parámetro no es válido. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Eliminar este calificador no es válido. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró el calificador especificado. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Se eliminó la invalidación local y el calificador del objeto primario original ha reanudado el ámbito. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) método.

Debido a las reglas de propagación de calificador, un calificador determinado puede haberse se hereda de otro objeto y simplemente se reemplaza en la clase o instancia actual. En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor original heredado. En este caso, la función devuelve el código de estado `WBEM_S_RESET_TO_DEFAULT`.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
