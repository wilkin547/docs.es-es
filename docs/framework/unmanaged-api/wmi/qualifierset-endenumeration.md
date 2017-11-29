---
title: "Función QualifierSet_EndEnumeration (referencia de API no administrada)"
description: "La función QualifierSet_EndEnumeration finaliza una enumeración."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a>QualifierSet_EndEnumeration (función)
Finaliza la enumeración iniciada con una llamada a la [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (función).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.

## <a name="return-value"></a>Valor devuelto

El siguiente valor devuelto por esta función se define en el *WbemCli.h* archivo de encabezado, o puede definirla como una constante en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) método.

Esta llamada se recomienda, pero no es necesario. Inmediatamente libera los recursos asociados a la enumeración.

## <a name="requirements"></a>Requisitos  

**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
**Encabezado:** WMINet_Utils.idl  
  
**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
