---
title: Función GetQualifierSet (Referencia de API no administrada)
description: La función GetQualifierSet recupera el calificador establecido para una clase o instancia.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176778"
---
# <a name="getqualifierset-function"></a>Función GetQualifierSet
Recupera el calificador establecido para una instancia o una definición de clase.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[en] Este parámetro no se utiliza.

`ptr`  
[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`ppQualSet`  
[fuera] Recibe el puntero de interfaz que permite el acceso a los calificadores del objeto de clase. El valor de `ppQualSet` no puede ser `null`. Si se produce un error, no se devuelve un nuevo objeto y el puntero se deja sin modificar.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Ha habido un fracaso general. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | El método especificado no existe. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insuficiente para completar la operación. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro `null`es . |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) método.

El [puntero IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al autor de la llamada agregar, editar o eliminar estos calificadores. Estos calificadores agregados, editados o eliminados se aplican a toda la definición de instancia o clase.

## <a name="requirements"></a>Requisitos  
**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
