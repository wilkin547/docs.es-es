---
title: IHostIoCompletionManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 90675d9be71342efa903767abbf63102b40a2c35
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804689"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager (Interfaz)
Proporciona métodos que permiten que el Common Language Runtime (CLR) interactúe con los puertos de finalización de e/s proporcionados por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Bind](ihostiocompletionmanager-bind-method.md)|Enlaza un identificador a un puerto de finalización de e/s.|  
|[Método CloseIoCompletionPort](ihostiocompletionmanager-closeiocompletionport-method.md)|Cierra un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort` .|  
|[Método CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md)|Solicita que el host cree un nuevo puerto de finalización de e/s.|  
|[Método GetAvailableThreads](ihostiocompletionmanager-getavailablethreads-method.md)|Obtiene el número de subprocesos de finalización de e/s que no están procesando actualmente solicitudes.|  
|[Método GetHostOverlappedSize](ihostiocompletionmanager-gethostoverlappedsize-method.md)|Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.|  
|[Método GetMaxThreads](ihostiocompletionmanager-getmaxthreads-method.md)|Obtiene el número máximo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.|  
|[Método GetMinThreads](ihostiocompletionmanager-getminthreads-method.md)|Obtiene el número mínimo de subprocesos que proporciona el host para las solicitudes de e/s de servicio.|  
|[Método InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md)|Proporciona al host la oportunidad de inicializar los datos personalizados sobre una solicitud de e/s.|  
|[Método SetCLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Proporciona al host un puntero de interfaz a una instancia de [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) implementada por CLR.|  
|[Método SetMaxThreads](ihostiocompletionmanager-setmaxthreads-method.md)|Establece el número máximo de subprocesos que el host asigna a las solicitudes de e/s de servicio.|  
|[Método SetMinThreads](ihostiocompletionmanager-setminthreads-method.md)|Establece el número mínimo de subprocesos que el host debe asignar a la finalización de e/s.|  
  
## <a name="remarks"></a>Observaciones  
 `IHostIoCompletionManager`corresponde a la `ICLRIoCompletionManager` interfaz implementada por CLR. CLR llama a los métodos de `IHostIoCompletionManager` para enlazar los identificadores a los puertos proporcionados por el host y el host llama a los métodos de `ICLRIoCompletionManager` para informar de la finalización de las solicitudes de e/s.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de hospedaje](hosting-interfaces.md)
