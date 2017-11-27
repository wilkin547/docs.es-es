---
title: "Función VerifyClientKey (referencia de API no administrada)"
description: "La función VerifyClientKey garantiza que la clave de cliente tiene la seguridad correcta."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: VerifyClientKey
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: VerifyClientKey
helpviewer_keywords: VerifyClientKey function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cce10e3dd5536a85b4dee62cc7f6e9e8e73929cb
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="verifyclientkey-function"></a>VerifyClientKey (función)
Garantiza que la clave de cliente tiene la seguridad correcta.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Valor devuelto

Si la función se realiza correctamente, el valor devuelto es `ERROR_SUCCESS` (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError.h*.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.def  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
