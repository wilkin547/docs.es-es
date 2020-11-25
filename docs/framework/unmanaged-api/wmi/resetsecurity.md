---
title: Función ResetSecurity (referencia de la API no administrada)
description: La función ResetSecurity asigna un token de suplantación al subproceso actual.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 259bef74356f16221f1453dd4086e2fbb26faa83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721119"
---
# <a name="resetsecurity-function"></a>Función ResetSecurity

Asigna el token de suplantación proporcionado para el subproceso actual.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a>Parámetros

`token`  
de El token de suplantación que se va a asociar al subproceso actual. Este valor puede ser `null`.

## <a name="return-value"></a>Valor devuelto

Si la función se ejecuta correctamente, el valor devuelto es `S_OK` (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero. Para obtener información de error extendida, llame a la función [GetErrorInfo](geterrorinfo.md) .
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
