---
title: Interfaces para generación de perfiles
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: dd6999e9f9e16264bde3cf62ce3a888841347607
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727476"
---
# <a name="profiling-interfaces"></a>Interfaces para generación de perfiles

En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>En esta sección  

 [ICLRProfiling (Interfaz)](iclrprofiling-interface.md)  
 Proporciona el método [AttachProfiler](iclrprofiling-attachprofiler-method.md) , que permite a un generador de perfiles asociarse a un proceso en ejecución.  
  
 [ICorProfilerAssemblyReferenceProvider (Interfaz)](icorprofilerassemblyreferenceprovider-interface.md)  
 Permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
 [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)  
 Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.  
  
 [ICorProfilerCallback2 (Interfaz)](icorprofilercallback2-interface.md)  
 Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.  
  
 [ICorProfilerCallback3 (Interfaz)](icorprofilercallback3-interface.md)  
 Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.  
  
 [ICorProfilerCallback4 (Interfaz)](icorprofilercallback4-interface.md)  
 Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.  
  
 [ICorProfilerCallback5 (interfaz)](icorprofilercallback5-interface.md)  
 Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.  
  
 [ICorProfilerCallback6 (Interfaz)](icorprofilercallback6-interface.md)  
 Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.  
  
 [Interfaz ICorProfilerCallback7](icorprofilercallback7-interface.md)  
 Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.  

[Interfaz ICorProfilerCallback8](icorprofilercallback8-interface.md)  
Proporciona métodos de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.

[Interfaz ICorProfilerCallback9](icorprofilercallback9-interface.md)  
Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha recopilado un método dinámico y que posteriormente se ha descargado.

 [ICorProfilerFunctionControl (Interfaz)](icorprofilerfunctioncontrol-interface.md)  
 Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.  
  
 [ICorProfilerFunctionEnum (Interfaz)](icorprofilerfunctionenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.  
  
 [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.  
  
 [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)  
 Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.  
  
 [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)  
 Extiende la `ICorProfilerInfo2` interfaz con los métodos admitidos en el .NET Framework 4 y versiones posteriores.  
  
 [ICorProfilerInfo4 (Interfaz)](icorprofilerinfo4-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.  
  
 [ICorProfilerInfo5 (Interfaz)](icorprofilerinfo5-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.  
  
 [Interfaz ICorProfilerInfo6](icorprofilerinfo6-interface.md)  
 Proporciona un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.  
  
 [Interfaz ICorProfilerInfo7](icorprofilerinfo7-interface.md)  
 Proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.  
  
 [ICorProfilerModuleEnum (Interfaz)](icorprofilermoduleenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.  
  
 [ICorProfilerObjectEnum (Interfaz)](icorprofilerobjectenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen.exe (generador de imágenes nativas)](../../tools/ngen-exe-native-image-generator.md).  
  
 [ICorProfilerThreadEnum (Interfaz)](icorprofilerthreadenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.  
  
 [IMethodMalloc (Interfaz)](imethodmalloc-interface.md)  
 Proporciona el método de [asignación](imethodmalloc-alloc-method.md) para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Información general sobre la generación de perfiles](profiling-overview.md)  
  
 [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)  
  
 [Enumeraciones para generación de perfiles](profiling-enumerations.md)  
  
 [Estructuras para generación de perfiles](profiling-structures.md)
