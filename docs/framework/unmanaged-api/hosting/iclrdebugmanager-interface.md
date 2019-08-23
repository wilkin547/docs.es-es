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
ms.openlocfilehash: 5a408995793caf879f8d5624ab727102c4859195
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959609"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager (Interfaz)
Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[BeginConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Establece una nueva conexión entre el host y el depurador para asociar las tareas con un identificador y un nombre descriptivo.|  
|[EndConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.|  
|[GetDacl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Este método no se implementa.|  
|[IsDebuggerAttached (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Obtiene un valor que indica si hay un depurador asociado al proceso.|  
|[SetConnectionTasks (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Asocia una lista de instancias de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) con un identificador y un nombre descriptivo.|  
|[SetDacl (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Este método no se implementa.|  
|[SetSymbolReadingPolicy (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Establece la Directiva para leer archivos de base de datos de programa (PDB). La Directiva determina si la información sobre los números de línea y los archivos se incluye en las pilas de llamadas.|  
  
## <a name="remarks"></a>Comentarios  
 En los escenarios de depuración, es posible que un host desee agrupar las tareas según su propia lógica de programación. Por ejemplo, una agrupación permitiría a un desarrollador ver solo las tareas requeridas por las API del desarrollador, en lugar de ver todas las tareas que se ejecutan en el proceso. `ICLRDebugManager`permite que el host implemente este tipo de agrupación.  
  
> [!IMPORTANT]
> Tres `ICLRDebugManager` métodos `BeginConnection` ,y`EndConnection`,dependen unos de otros. `SetConnectionTasks` Se les debe llamar en el orden especificado para que funcionen según lo previsto.  
  
 La agrupación, y los identificadores y nombres descriptivos que el host asigna a la agrupación, no tienen ningún significado para el Common Language Runtime (CLR). CLR simplemente pasa la información junto con el depurador.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
