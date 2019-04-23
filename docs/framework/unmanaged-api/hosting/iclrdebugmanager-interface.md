---
title: ICLRDebugManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22c3a480e2b68377e300df1083b3178ee4e2d2a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198847"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager (Interfaz)
Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Establece una nueva conexión entre el host y el depurador para asociar tareas a un identificador y un nombre descriptivo.|  
|[EndConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.|  
|[GetDacl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Este método no se implementa.|  
|[IsDebuggerAttached (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Obtiene un valor que indica si hay un depurador asociado al proceso.|  
|[SetConnectionTasks (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Asocia una lista de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancias con un identificador y un nombre descriptivo.|  
|[SetDacl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Este método no se implementa.|  
|[SetSymbolReadingPolicy (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Establece la directiva para leer los archivos de programa (PDB) de la base de datos. La directiva determina si se incluye información sobre archivos y números de línea en las pilas de llamadas.|  
  
## <a name="remarks"></a>Comentarios  
 En escenarios de depuración, un host podría desear agrupar las tareas según su propia lógica de programación. Por ejemplo, una agrupación permitiría que un desarrollador ver solo las tareas necesarias de las API del desarrollador, en lugar de ver todas las tareas que se ejecutan en el proceso. `ICLRDebugManager` permite al host implementar este tipo de agrupación.  
  
> [!IMPORTANT]
>  Tres `ICLRDebugManager` métodos, `BeginConnection`, `SetConnectionTasks` y `EndConnection`, son dependientes entre sí. Se debe llamar en el orden especificado para que funcione según lo previsto.  
  
 La agrupación y los identificadores y nombres descriptivos que el host se asigna a la agrupación, no tienen ningún significado para common language runtime (CLR). El CLR simplemente pasa la información al depurador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
