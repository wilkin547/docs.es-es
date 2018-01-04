---
title: "Función QualifierSet_Next (referencia de API no administrada)"
description: "La función QualifierSet_Next recupera el siguiente calificador en una enumeración."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Next
helpviewer_keywords: QualifierSet_Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 01a9c9d162039547849597aaa9c8a6fa38a31455
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next (función)
Recupera el siguiente calificador en una enumeración que se inició con una llamada a la [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (función).   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
[in] Este parámetro no se utiliza.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.

`lFlags`   
[in] Reservado. Este parámetro debe ser 0.

`pstrName`   
[out] El nombre del calificador. Si `null`, este parámetro se omite; en caso contrario, `pstrName` no debe apuntar a válido `BSTR` o se produce una pérdida de memoria. Si no es null, la función siempre asigna un nuevo `BSTR` cuando devuelve `WBEM_S_NO_ERROR`.

`pVal`   
[out] Cuando se realiza correctamente, el valor del calificador. Si se produce un error en la función, el `VARIANT` que señala `pVal` no se modifica. Si este parámetro es `null`, se omite el parámetro.

`plFlavor`   
[out] Un puntero a un valor largo que recibe el tipo de calificador. Si no se desea obtener información de tipo, este parámetro puede ser `null`. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | El llamador no llamó a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No hay más calificadores se mantienen en la enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) método.

Se llama a la `QualifierSet_Next` función repetidamente para enumerar todos los calificadores hasta que el valor devuelto de función `WBEM_S_NO_MORE_DATA`. Para finalizar la enumeración al principio, llame a la [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) (función).

El orden de los calificadores que se devuelve durante la enumeración es indefinido.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
