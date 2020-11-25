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
ms.openlocfilehash: 2000de77903c3dabb43116fa1700b4ed393aeb5a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721158"
---
# <a name="qualifierset_delete-function"></a>Función QualifierSet_Delete

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

`ptr` de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName` de Nombre del calificador que se va a eliminar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | El parámetro `wszName` no es válido. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | No se pudo eliminar este calificador. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró el calificador especificado. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Se eliminó la invalidación local y el calificador original del objeto primario ha reanudado el ámbito. |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet::D iminar](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) .

Debido a las reglas de propagación del calificador, un calificador determinado se puede haber heredado de otro objeto y simplemente se ha invalidado en la clase o instancia actual. En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor heredado original. En este caso, la función devuelve el código de estado `WBEM_S_RESET_TO_DEFAULT` .

## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
