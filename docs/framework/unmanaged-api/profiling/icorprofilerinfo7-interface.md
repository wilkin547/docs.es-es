---
title: Interfaz ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 0e9f76717aeff27e863245faac241927e7495076
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495494"
---
# <a name="icorprofilerinfo7-interface"></a>Interfaz ICorProfilerInfo7
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Una subclase de [ICorProfilerInfo6](icorprofilerinfo6-interface.md) que proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ApplyMetaData](icorprofilerinfo7-applymetadata-method.md)|Aplica los metadatos recién definidos por los `IMetadataEmit::Define*` métodos a un módulo especificado.|  
|[Método GetInMemorySymbolsLength](icorprofilerinfo7-getinmemorysymbolslength-method.md)|Devuelve la longitud de una secuencia de símbolos en memoria.|  
|[ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)|Lee bytes de una secuencia de símbolos en memoria.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces para generación de perfiles](profiling-interfaces.md)
