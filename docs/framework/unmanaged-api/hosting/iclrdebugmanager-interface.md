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
ms.openlocfilehash: 717a3d12528a34eafbd918c29d8e13bb87097d82
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615787"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager (Interfaz)
Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BeginConnection](iclrdebugmanager-beginconnection-method.md)|Establece una nueva conexión entre el host y el depurador para asociar las tareas con un identificador y un nombre descriptivo.|  
|[Método EndConnection](iclrdebugmanager-endconnection-method.md)|Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.|  
|[Método GetDacl](iclrdebugmanager-getdacl-method.md)|Este método no se implementa.|  
|[Método IsDebuggerAttached](iclrdebugmanager-isdebuggerattached-method.md)|Obtiene un valor que indica si hay un depurador asociado al proceso.|  
|[Método SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Asocia una lista de instancias de [ICLRTask](iclrtask-interface.md) con un identificador y un nombre descriptivo.|  
|[Método SetDacl](iclrdebugmanager-setdacl-method.md)|Este método no se implementa.|  
|[Método SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md)|Establece la Directiva para leer archivos de base de datos de programa (PDB). La Directiva determina si la información sobre los números de línea y los archivos se incluye en las pilas de llamadas.|  
  
## <a name="remarks"></a>Observaciones  
 En los escenarios de depuración, es posible que un host desee agrupar las tareas según su propia lógica de programación. Por ejemplo, una agrupación permitiría a un desarrollador ver solo las tareas requeridas por las API del desarrollador, en lugar de ver todas las tareas que se ejecutan en el proceso. `ICLRDebugManager`permite que el host implemente este tipo de agrupación.  
  
> [!IMPORTANT]
> Tres `ICLRDebugManager` métodos, `BeginConnection` `SetConnectionTasks` y, `EndConnection` dependen unos de otros. Se les debe llamar en el orden especificado para que funcionen según lo previsto.  
  
 La agrupación, y los identificadores y nombres descriptivos que el host asigna a la agrupación, no tienen ningún significado para el Common Language Runtime (CLR). CLR simplemente pasa la información junto con el depurador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de hospedaje](hosting-interfaces.md)
