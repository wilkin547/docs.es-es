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
ms.openlocfilehash: db6a20dee21b6c8bbd55fa9b52a159a00fe310d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092038"
---
# <a name="waitortimercallback-function-pointer"></a>puntero a la función WAITORTIMERCALLBACK
Señala a una función que notifica al host que un identificador de espera (<xref:System.Threading.WaitHandle>) se ha señalado o ha agotado el tiempo de espera.  
  
 Este puntero de función ha quedado en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `lpParameter`  
 de Un puntero a un objeto que contiene información definida por el host.  
  
 `TimerOrWaitFired`  
 [in] `true` si el identificador de espera ha agotado el tiempo de espera o `false` si se ha señalado.  
  
## <a name="remarks"></a>Comentarios  
 Función a la que `WAITORTIMERCALLBACK` puntos es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorWks. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
