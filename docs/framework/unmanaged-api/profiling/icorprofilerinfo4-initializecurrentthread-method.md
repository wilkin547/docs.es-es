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
ms.openlocfilehash: f5a4a6bc7b1e79068b11b099352cec64dd09f301
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459458"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread (Método)
Inicializa el subproceso actual antes de generador de perfiles posterior llamadas de API en el mismo subproceso, por lo que se puede evitar que un interbloqueo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Comentarios  
 Se recomienda llamar a `InitializeCurrentThread` en cualquier subproceso que llama a un generador de perfiles API mientras haya suspendido subprocesos. Este método se utiliza normalmente los generadores de perfiles de muestreo que crear sus propios subprocesos para llamar a la [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) se explica el método para realizar la pila mientras se suspende el subproceso de destino. Mediante una llamada a `InitializeCurrentThread` una vez cuando el generador de perfiles crea primero el subproceso de muestreo, los generadores de perfiles pueden asegurarse de que la inicialización diferida por cada subproceso que CLR lo contrario se realizaría durante la primera llamada a `DoStackSnapshot` puede llevarse a cabo sin ningún riesgo cuando otros subprocesos no están suspendido.  
  
> [!NOTE]
>  `InitializeCurrentThread` realiza la inicialización de antemano para finalizar las tareas que adoptan bloqueos y pueden generar un interbloqueo. Llamar a `InitializeCurrentThread` cuando no haya ningún subproceso suspendido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
