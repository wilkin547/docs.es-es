---
title: Interfaces para generación de perfiles
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: adc47417265d32d79508af949c118c4d31a83365
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124197"
---
# <a name="profiling-interfaces"></a>Interfaces para generación de perfiles
En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>En esta sección  
 [ICLRProfiling (interfaz)](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 Proporciona el método [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) , que permite a un generador de perfiles asociarse a un proceso en ejecución.  
  
 [ICorProfilerAssemblyReferenceProvider (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 Permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .  
  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.  
  
 [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.  
  
 [ICorProfilerCallback3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.  
  
 [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.  
  
 [ICorProfilerCallback5 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.  
  
 [ICorProfilerCallback6 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.  
  
 [ICorProfilerCallback7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.  

[ICorProfilerCallback8 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
Proporciona métodos de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.

[ICorProfilerCallback9 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha recopilado un método dinámico y que posteriormente se ha descargado.

 [ICorProfilerFunctionControl (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.  
  
 [ICorProfilerFunctionEnum (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.  
  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.  
  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.  
  
 [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 Extiende la interfaz de `ICorProfilerInfo2` con métodos admitidos en el .NET Framework 4 y versiones posteriores.  
  
 [ICorProfilerInfo4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.  
  
 [ICorProfilerInfo5 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.  
  
 [ICorProfilerInfo6 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 Proporciona un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.  
  
 [ICorProfilerInfo7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 Proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.  
  
 [ICorProfilerModuleEnum (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.  
  
 [ICorProfilerObjectEnum (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen. exe (generador de imágenes nativas)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
 [ICorProfilerThreadEnum (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.  
  
 [IMethodMalloc (interfaz)](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 Proporciona el método de [asignación](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Información general sobre la generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Estructuras para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
