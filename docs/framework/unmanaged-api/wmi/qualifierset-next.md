---
title: función QualifierSet_Next (Referencia de API no administrada)
description: La función QualifierSet_Next recupera el siguiente calificador de una enumeración.
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
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174880"
---
# <a name="qualifierset_next-function"></a>Función QualifierSet_Next
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

`vFunc`[en] Este parámetro no se utiliza.

`ptr`[en] Puntero a una instancia de [IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

`lFlags`[en] Reservados. Este parámetro debe ser 0.

`pstrName`[fuera] El nombre del calificador. Si `null`, se omite este parámetro; de `pstrName` lo contrario, no `BSTR` debe apuntar a una pérdida de memoria válida o se produce una pérdida de memoria. Si no es null, la `BSTR` función `WBEM_S_NO_ERROR`siempre asigna un nuevo cuando devuelve .

`pVal`[fuera] Cuando se realiza correctamente, el valor del calificador. Si se produce `VARIANT` un error `pVal` en la función, no se modifica el punto por. Si este `null`parámetro es , se omite el parámetro.

`plFlavor`[fuera] Un puntero a un LONG que recibe el sabor del calificador. Si no se desea información de `null`sabor, este parámetro puede ser .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | El autor de la llamada no llamó a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No quedan más calificadores en la enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) método.

Llamar a `QualifierSet_Next` la función repetidamente para enumerar todos `WBEM_S_NO_MORE_DATA`los calificadores hasta que la función devuelve . Para finalizar la enumeración antes de tiempo, llame a la [función QualifierSet_EndEnumeration.](qualifierset-endenumeration.md)

El orden de los calificadores devueltos durante la enumeración es indefinido.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
