---
title: ICLRTask2::EndPreventAsyncAbort (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 7f8963403c60815bbf1cd3008ed7fec73d849fea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720261"
---
# <a name="iclrtask2endpreventasyncabort-method"></a>ICLRTask2::EndPreventAsyncAbort (Método)

Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|HOST_E_INVALIDOPERATION|Se llamó al método en un subproceso que no es el subproceso actual.|  
  
## <a name="remarks"></a>Comentarios  

 Al llamar a este método, se reduce el contador Delay-Thread-Abort del subproceso actual en uno.  
  
 Las llamadas a [ICLRTask2:: BeginPreventAsyncAbort (](iclrtask2-beginpreventasyncabort-method.md) y `EndPreventAsyncAbort` se pueden anidar. Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.  
  
 La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM). El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente. Del mismo modo, no se comprueba el desbordamiento del contador interno. Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md)
- [ICLRTask2 (Interfaz)](iclrtask2-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
