---
title: Interfaz ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4c7e94ffa60bcfaead009e1a8baa9b54b2e8ab7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125052"
---
# <a name="icorprofilerinfo7-interface"></a>Interfaz ICorProfilerInfo7
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Una subclase de [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) que proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ApplyMetaData (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|Aplica los metadatos recién definidos por los métodos `IMetadataEmit::Define*` a un módulo especificado.|  
|[GetInMemorySymbolsLength (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|Devuelve la longitud de una secuencia de símbolos en memoria.|  
|[ReadInMemorySymbols](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|Lee bytes de una secuencia de símbolos en memoria.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
