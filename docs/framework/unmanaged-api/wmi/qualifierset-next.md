---
title: Función QualifierSet_Next (referencia de la API no administrada)
description: La función QualifierSet_Next recupera el calificador siguiente en una enumeración.
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
ms.openlocfilehash: 54d79a3dc081e9cdcb42153b6f7aa457557e3399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721132"
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

`vFunc` de Este parámetro no se utiliza.

`ptr` de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags` de Sector. Este parámetro debe ser 0.

`pstrName` enuncia Nombre del calificador. Si `null` es, este parámetro se omite; de lo contrario, `pstrName` no debe apuntar a un válido `BSTR` o se produce una fuga de memoria. Si no es null, la función siempre asigna un nuevo `BSTR` cuando devuelve `WBEM_S_NO_ERROR` .

`pVal` enuncia Cuando se realiza correctamente, el valor del calificador. Si se produce un error en la función, el `VARIANT` señalado por `pVal` no se modifica. Si este parámetro es `null` , se omite el parámetro.

`plFlavor` enuncia Un puntero a un LONG que recibe el tipo de calificador. Si no se desea información de tipo, este parámetro puede ser `null` .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | El autor de la llamada no llama a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | No quedan más calificadores en la enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .

Llame a la `QualifierSet_Next` función varias veces para enumerar todos los calificadores hasta que la función devuelva `WBEM_S_NO_MORE_DATA` . Para finalizar la enumeración pronto, llame a la función [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .

El orden de los calificadores devueltos durante la enumeración es indefinido.

## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
