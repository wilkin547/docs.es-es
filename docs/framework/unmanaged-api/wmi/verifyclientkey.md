---
title: Función VerifyClientKey (referencia de API no administrada)
description: La función VerifyClientKey garantiza que la clave de cliente tiene la seguridad correcta.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b51fe4510f4172227d9afd049eb6815790a165
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783087"
---
# <a name="verifyclientkey-function"></a>Función VerifyClientKey
Garantiza que la clave de cliente cuenta con la seguridad adecuada.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Valor devuelto

Si la función se realiza correctamente, el valor devuelto es `ERROR_SUCCESS` (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError.h*.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.def  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
