---
title: ICLRDebugManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e712f22156e96cfc58e9c1a835077ba21ecd184
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager (Interfaz)
Proporciona métodos que permiten a un host asociar un conjunto de tareas a un identificador y un nombre descriptivo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Establece una nueva conexión entre el host y el depurador para asociar tareas a un identificador y un nombre descriptivo.|  
|[EndConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.|  
|[GetDacl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Este método no se implementa.|  
|[IsDebuggerAttached (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Obtiene un valor que indica si hay un depurador asociado al proceso.|  
|[SetConnectionTasks (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Asocia una lista de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancias con un identificador y un nombre descriptivo.|  
|[SetDacl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Este método no se implementa.|  
|[SetSymbolReadingPolicy (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Establece la directiva para leer los archivos de programa (PDB) de la base de datos. La directiva determina si se incluye información sobre los números de línea y los archivos en las pilas de llamadas.|  
  
## <a name="remarks"></a>Comentarios  
 En escenarios de depuración, un host podría desear agrupar las tareas según su propia lógica de programación. Por ejemplo, una agrupación permitiría que un desarrollador ver solo las tareas necesarias con las API del desarrollador, en lugar de ver todas las tareas de ejecución en el proceso. `ICLRDebugManager`permite al host implementar este tipo de agrupación.  
  
> [!IMPORTANT]
>  Tres `ICLRDebugManager` métodos, `BeginConnection`, `SetConnectionTasks` y `EndConnection`, son dependientes entre sí. Se debe llamar en el orden especificado para que funcione según lo previsto.  
  
 La agrupación y los identificadores y nombres descriptivos que el host se asigna a la agrupación, no tienen ningún significado para common language runtime (CLR). El CLR simplemente pasa la información al depurador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
