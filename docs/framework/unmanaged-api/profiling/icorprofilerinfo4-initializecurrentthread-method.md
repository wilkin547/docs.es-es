---
title: ICorProfilerInfo4::InitializeCurrentThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fd0900e61c57d105439d83430284dc8634d2a1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223607"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread (Método)
Inicializa el subproceso actual antes del generador de perfiles posteriores llamadas de API en el mismo subproceso, por lo que se puede evitar que un interbloqueo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Comentarios  
 Se recomienda que llame a `InitializeCurrentThread` en cualquier subproceso que llama a un generador de perfiles de API, aunque hay suspende subprocesos. Este método se utiliza normalmente los generadores de perfiles de muestreo que crear sus propios subprocesos para llamar a la [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) método para realizar la pila guiará mientras se suspende el subproceso de destino. Mediante una llamada a `InitializeCurrentThread` una vez cuando el generador de perfiles crea primero el subproceso de muestreo, pueden asegurarse de que la inicialización diferida por subproceso que CLR en caso contrario, se pueden realizar durante la primera llamada a los generadores de perfiles `DoStackSnapshot` puede llevarse a cabo sin ningún riesgo cuando otros subprocesos no están suspendido.  
  
> [!NOTE]
>  `InitializeCurrentThread` realiza la inicialización de antemano para finalizar las tareas que se adoptan bloqueos y pueden causar interbloqueos. Llamar a `InitializeCurrentThread` sólo cuando no hay ningún subproceso suspendido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
