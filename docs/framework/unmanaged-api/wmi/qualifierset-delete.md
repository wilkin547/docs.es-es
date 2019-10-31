---
title: Función QualifierSet_Delete (referencia de la API no administrada)
description: La función QualifierSet_Delete elimina un calificador por nombre.
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
ms.openlocfilehash: e7bedcb5c56f9976f8dfd2619081971075d0d809
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127297"
---
# <a name="qualifierset_delete-function"></a>QualifierSet_Delete función)
Elimina un calificador específico por el nombre.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
de Este parámetro no se utiliza.

`ptr`   
de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName`   
de Nombre del calificador que se va a eliminar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | El parámetro `wszName` no es válido. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | No se pudo eliminar este calificador. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró el calificador especificado. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Se eliminó la invalidación local y el calificador original del objeto primario ha reanudado el ámbito. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet::D iminar](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) .

Debido a las reglas de propagación del calificador, un calificador determinado se puede haber heredado de otro objeto y simplemente se ha invalidado en la clase o instancia actual. En este caso, el método `QualifierSet_Delete` restablece el calificador a su valor heredado original. En este caso, la función devuelve el código de estado `WBEM_S_RESET_TO_DEFAULT`.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
