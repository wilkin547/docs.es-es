---
title: Función QualifierSet_Get (referencia de la API no administrada)
description: La función QualifierSet_Get obtiene un calificador con nombre.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd096287b85b4a51a8cae85dddcca95cc1a8dbae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721145"
---
# <a name="qualifierset_get-function"></a>Función QualifierSet_Get

Obtiene el calificador con nombre especificado.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>Parámetros

`vFunc` de Este parámetro no se utiliza.

`ptr` de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`wszName` de Nombre del calificador cuyo valor se solicita.

`lFlags` de Sector. Este parámetro debe ser 0.

`pVal` enuncia Cuando se realiza correctamente, el tipo y el valor correctos para el calificador. Si se produce un error en la función, el `VARIANT` señalado por `pVal` no se modifica. Si este parámetro es `null` , se omite el parámetro.

`plFlavor` enuncia Un puntero a un LONG que recibe los bits de sabor del calificador para el calificador solicitado. Si no se desea información de tipo, este parámetro puede ser `null` .

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | El calificador especificado no existe. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet:: get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) .

## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
