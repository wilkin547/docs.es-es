---
title: ICorProfilerCallback3::ProfilerDetachSucceeded (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
ms.openlocfilehash: b9b284de102dc75a637803ca5be0f2769da452ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730323"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a>ICorProfilerCallback3::ProfilerDetachSucceeded (Método)

Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a>Valor devuelto  

 Se omite el valor devuelto por esta devolución de llamada.  
  
## <a name="remarks"></a>Comentarios  

 La devolución de llamada `ProfilerDetachSucceeded` se emite después de que todos los subprocesos han salido del código del generador de perfiles. Cuando se llama a este método, el generador de perfiles debe realizar tareas de última hora que no son adecuadas para su destructor, tales como notificar a su interfaz de usuario o registrar componentes. Sin embargo, el generador de perfiles no debe llamar a las funciones de las interfaces proporcionadas por el CLR durante esta devolución de llamada (como la [ICorProfilerInfo](icorprofilerinfo-interface.md) o las `IMetaData*` interfaces).  
  
 El CLR crea una entrada en el registro de eventos de aplicación de Windows para indicar que la operación de desasociación ha sido correcta.  
  
 Después de que el generador de perfiles vuelva de esta devolución de llamada, el CLR libera el objeto de generador de perfiles y descarga el archivo DLL del generador de perfiles. Por lo tanto, el generador de perfiles no debe realizar acciones que puedan hacer que la ejecución se realice dentro del archivo DLL del generador de perfiles después de que vuelva de esta devolución de llamada. Por ejemplo, no debe crear subprocesos ni registrar devoluciones de llamada de temporizador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de metadatos](../metadata/metadata-interfaces.md)
- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
