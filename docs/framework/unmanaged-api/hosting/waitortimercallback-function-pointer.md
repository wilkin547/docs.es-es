---
description: 'Más información sobre: puntero de función WAITORTIMERCALLBACK'
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
ms.openlocfilehash: 6fd9e7eab56e48086eefcb26fc48cbf5f45d4a0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679061"
---
# <a name="waitortimercallback-function-pointer"></a>puntero a la función WAITORTIMERCALLBACK

Señala a una función que notifica al host que un identificador de espera ( <xref:System.Threading.WaitHandle> ) se ha señalado o ha agotado el tiempo de espera.  
  
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
 [in] `true` Si el identificador de espera ha agotado el tiempo de espera, o `false` si se ha señalado.  
  
## <a name="remarks"></a>Observaciones  

 La función a la que `WAITORTIMERCALLBACK` apunta es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorWks.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
