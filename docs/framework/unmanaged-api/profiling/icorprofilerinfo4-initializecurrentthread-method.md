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
ms.openlocfilehash: b52a0e7f993629c1005883723c734996d75300a7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868439"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread (Método)
Inicializa el subproceso actual antes de las llamadas posteriores a la API del generador de perfiles en el mismo subproceso, de modo que se pueda evitar el interbloqueo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Notas  
 Se recomienda llamar a `InitializeCurrentThread` en cualquier subproceso que llame a una API del generador de perfiles mientras haya subprocesos suspendidos. Este método lo suelen usar los profileres de muestreo que crean su propio subproceso para llamar al método [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) para realizar los recorridos de la pila mientras se suspende el subproceso de destino. Mediante una llamada a `InitializeCurrentThread` una vez cuando el generador de perfiles crea primero el subproceso de muestreo, los perfiles pueden asegurarse de que la inicialización diferida por subproceso que CLR llevaría a cabo en la primera llamada a `DoStackSnapshot` ahora puede producirse de forma segura cuando no se suspende ningún otro subproceso.  
  
> [!NOTE]
> `InitializeCurrentThread` realiza la inicialización de antemano para finalizar las tareas que toman bloqueos y pueden interbloquearse. Llame a `InitializeCurrentThread` solo cuando no haya subprocesos suspendidos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo4 (interfaz)](icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
