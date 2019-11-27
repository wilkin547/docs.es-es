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
ms.openlocfilehash: 39882a554f9d47040bef00ff320d15b56abea533
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445714"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread (Método)
Inicializa el subproceso actual antes de las llamadas posteriores a la API del generador de perfiles en el mismo subproceso, de modo que se pueda evitar el interbloqueo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Comentarios  
 Se recomienda llamar a `InitializeCurrentThread` en cualquier subproceso que llame a una API del generador de perfiles mientras haya subprocesos suspendidos. Este método lo suelen usar los profileres de muestreo que crean su propio subproceso para llamar al método [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) para realizar los recorridos de la pila mientras se suspende el subproceso de destino. Mediante una llamada a `InitializeCurrentThread` una vez cuando el generador de perfiles crea primero el subproceso de muestreo, los perfiles pueden asegurarse de que la inicialización diferida por subproceso que CLR llevaría a cabo en la primera llamada a `DoStackSnapshot` ahora puede producirse de forma segura cuando no se suspende ningún otro subproceso.  
  
> [!NOTE]
> `InitializeCurrentThread` realiza la inicialización de antemano para finalizar las tareas que toman bloqueos y pueden interbloquearse. Llame a `InitializeCurrentThread` solo cuando no haya subprocesos suspendidos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
