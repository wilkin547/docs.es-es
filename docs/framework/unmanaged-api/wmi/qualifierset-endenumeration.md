---
title: Función QualifierSet_EndEnumeration (referencia de la API no administrada)
description: La función QualifierSet_EndEnumeration finaliza una enumeración.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2739003fc9c1f93d379e4a59338cbef7a1a0f135
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726748"
---
# <a name="qualifierset_endenumeration-function"></a>Función QualifierSet_EndEnumeration

Finaliza la enumeración iniciada con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
de Este parámetro no se utiliza.

`ptr` de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

## <a name="return-value"></a>Valor devuelto

El siguiente valor devuelto por esta función se define en el archivo de encabezado *WbemCli. h* , o bien se puede definir como una constante en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .

Se recomienda esta llamada, pero no es necesaria. Libera inmediatamente los recursos asociados a la enumeración.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
**Encabezado:** WMINet_Utils. idl  
  
**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
