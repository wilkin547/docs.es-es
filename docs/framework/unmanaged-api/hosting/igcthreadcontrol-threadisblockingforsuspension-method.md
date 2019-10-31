---
title: IGCThreadControl::ThreadIsBlockingForSuspension (Método)
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: e6534c3085b70b590c2dcc3f50cf0253bd5e6682
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134746"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a>IGCThreadControl::ThreadIsBlockingForSuspension (Método)
Notifica al host que el subproceso que está realizando la llamada está a punto de bloquearse, quizás para una recolección de elementos no utilizados u otra suspensión.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a>Comentarios  
 El host puede elegir dentro de la devolución de llamada de `ThreadIsBlockingForSuspension` si se va a volver a programar un subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCThreadControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
