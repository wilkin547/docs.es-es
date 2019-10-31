---
title: Función GetQualifierSet (referencia de la API no administrada)
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
ms.openlocfilehash: 489e240af3f26e82f2459ac4b4dbd944639f78fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127448"
---
# <a name="getqualifierset-function"></a>GetQualifierSet función)
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
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`ppQualSet`  
enuncia Recibe el puntero de interfaz que permite el acceso a los calificadores del objeto de clase. El valor de `ppQualSet` no puede ser `null`. Si se produce un error, no se devuelve un nuevo objeto y el puntero se deja sin modificar. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Se ha producido un error general. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | El método especificado no existe. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro es `null`. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemClassObject:: GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) . 

El [puntero IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al autor de la llamada agregar, editar o eliminar estos calificadores. Tales calificadores agregados, editados o eliminados se aplican a la definición de clase o instancia completa.

## <a name="requirements"></a>Requisitos  
**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
