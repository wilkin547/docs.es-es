---
title: puntero a la función WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65af5303468904ee40da4d567381782af70bfb38
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776501"
---
# <a name="waitortimercallback-function-pointer"></a>puntero a la función WAITORTIMERCALLBACK
Señala a una función que notifica al host que un identificador de una espera (<xref:System.Threading.WaitHandle>) se ha señalado o tiempo de espera.  
  
 Este puntero de función ha quedado obsoleto en .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `lpParameter`  
 [in] Un puntero a un objeto que contiene la información definida por el host.  
  
 `TimerOrWaitFired`  
 [in] `true` si el identificador de espera agotado, o `false` si estaba señalado.  
  
## <a name="remarks"></a>Comentarios  
 La función a la que `WAITORTIMERCALLBACK` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación de hospedaje.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorWks.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
