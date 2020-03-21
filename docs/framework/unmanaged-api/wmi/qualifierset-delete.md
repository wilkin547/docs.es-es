---
title: función QualifierSet_Delete (Referencia de API no administrada)
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
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174906"
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
[en] Este parámetro no se utiliza.

`ptr`[en] Puntero a una instancia de [IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

`wszName`[en] El nombre del calificador que se ha eliminado.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | El parámetro `wszName` no es válido. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Eliminar este calificador es ilegal. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró el calificador especificado. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Se eliminó la invalidación local y el calificador original del objeto primario ha reanudado el ámbito. |

## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) método.

Debido a las reglas de propagación de calificadores, un calificador determinado puede haber sido heredado de otro objeto y simplemente invalidado en la clase o instancia actual. En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor heredado original. La función en este `WBEM_S_RESET_TO_DEFAULT`caso devuelve el código de estado .

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
