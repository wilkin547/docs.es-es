---
title: Función VerifyClientKey (referencia de la API no administrada)
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
ms.openlocfilehash: 0a0680651eb192e2798ede00048599c5130e63f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107355"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey función)
Garantiza que la clave de cliente cuenta con la seguridad adecuada.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Valor devuelto

Si la función se ejecuta correctamente, el valor devuelto es `ERROR_SUCCESS` (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError. h*.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. def  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
