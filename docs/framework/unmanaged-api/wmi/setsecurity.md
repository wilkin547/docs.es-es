---
title: Función SetSecurity (referencia de API no administrada)
description: La función SetSecurity recupera el token de suplantación del subproceso actual.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b3e8ddb34849611daae4dfa1d2762a25ac5cf82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721150"
---
# <a name="setsecurity-function"></a>Función SetSecurity
Recupera el token de suplantación asociado al subproceso actual.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a>Parámetros

`pNeedToReset` [out] Cuando la función devuelve, contiene un puntero a un `boolean` que indica si se debe restablecer el token mediante una llamada a la [ResetSecurity](resetsecurity.md) función.  

`token`  
[out] La función devuelve, contiene un puntero al identificador del token de suplantación asociado al subproceso actual. Su valor puede ser `null` si no hay ningún testigo asociado con el subproceso actual. 

## <a name="return-value"></a>Valor devuelto

Si la función se realiza correctamente, el valor devuelto es `S_OK` (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero. Para obtener información de error extendida, llame a la [GetErrorInfo](geterrorinfo.md) función.
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también
- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
