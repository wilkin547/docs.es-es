---
title: Función QualifierSet_Next (referencia de API no administrada)
description: La función QualifierSet_Next recupera el siguiente calificador en una enumeración.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ac5cc8633881749bdc167e1b3925a83f7adf3b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760302"
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next function
Recupera el siguiente calificador en una enumeración que se inició con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`   
[in] Este parámetro se usa.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.

`lFlags`   
[in] Reservado. Este parámetro debe ser 0.

`pstrName`   
[out] El nombre del calificador. Si `null`, este parámetro se omite; en caso contrario, `pstrName` no debe apuntar a una `BSTR` o se produce una pérdida de memoria. Si no es null, la función siempre asigna un nuevo `BSTR` cuando devuelve `WBEM_S_NO_ERROR`.

`pVal`   
[out] Cuando se realiza correctamente, el valor del calificador. Si se produce un error en la función, el `VARIANT` apunta `pVal` no se modifica. Si este parámetro es `null`, se omite el parámetro.

`plFlavor`   
[out] Un puntero a un valor largo que recibe el tipo de calificador. Si no se desea obtener información de tipo, este parámetro puede ser `null`. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |DESCRIPCIÓN  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | El llamador no llamó a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No hay más calificadores se mantienen en la enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) método.

Se llama a la `QualifierSet_Next` función varias veces para enumerar todos los calificadores hasta que el valor devuelto de función `WBEM_S_NO_MORE_DATA`. Para finalizar la enumeración al principio, llame a la [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) función.

El orden de los calificadores que ha devuelto durante la enumeración es indefinido.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
