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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c3bebe8eabd4d5fd5faec21e0b0efc408353bc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197274"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para interactuar con los puertos de terminación de E/S proporcionados por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Bind (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Enlaza un identificador a un puerto de terminación de E/S.|  
|[CloseIoCompletionPort (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Cierra un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort`.|  
|[CreateIoCompletionPort (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Solicita que el host cree un nuevo puerto de terminación de E/S.|  
|[GetAvailableThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Obtiene el número de subprocesos de finalización de E/S que no se están procesando actualmente las solicitudes.|  
|[GetHostOverlappedSize (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de E/S.|  
|[GetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Obtiene el número máximo de subprocesos que el host puede asignar para atender las solicitudes de E/S.|  
|[GetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Obtiene el número mínimo de subprocesos que proporciona el host para atender las solicitudes de E/S.|  
|[InitializeHostOverlapped (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Proporciona una oportunidad para inicializar los datos personalizados sobre una solicitud de E/S al host.|  
|[SetCLRIoCompletionManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Proporciona el host con un puntero de interfaz a un [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instancia implementada por CLR.|  
|[SetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Establece el número máximo de subprocesos que el host asigna para atender las solicitudes de E/S.|  
|[SetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Establece el número mínimo de subprocesos que el host debe asignar a la finalización de E/S.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostIoCompletionManager` corresponde a la `ICLRIoCompletionManager` interfaz implementada por CLR. CLR llama a los métodos de `IHostIoCompletionManager` para enlazar los identificadores a los puertos que proporciona el host y el host llama a los métodos de `ICLRIoCompletionManager` para notificar la finalización de las solicitudes de E/S.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
