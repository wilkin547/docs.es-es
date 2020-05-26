---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: f7cdc3fe9d52db56d0280bc602d3a9f2f54e8246
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805250"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a>IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)
Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a>Observaciones  
 `ThreadIsBlockingForDebugger`Siempre se llamará al método en un subproceso en tiempo de ejecución.  
  
 El `ThreadIsBlockingForDebugger` método proporciona al host una oportunidad para realizar otra acción mientras el subproceso se bloquea.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IDebuggerThreadControl (Interfaz)](idebuggerthreadcontrol-interface.md)
