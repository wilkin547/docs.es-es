---
title: Interfaces para generación de perfiles
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: 8b6b9acff2945e2d8fd684bfa31e4af086ea5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868153"
---
# <a name="profiling-interfaces"></a>Interfaces para generación de perfiles
En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>Esta sección  
 [ICLRProfiling (interfaz)](iclrprofiling-interface.md)  
 Proporciona el método [AttachProfiler](iclrprofiling-attachprofiler-method.md) , que permite a un generador de perfiles asociarse a un proceso en ejecución.  
  
 [ICorProfilerAssemblyReferenceProvider (interfaz)](icorprofilerassemblyreferenceprovider-interface.md)  
 Permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
 [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)  
 Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.  
  
 [ICorProfilerCallback2 (interfaz)](icorprofilercallback2-interface.md)  
 Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.  
  
 [ICorProfilerCallback3 (interfaz)](icorprofilercallback3-interface.md)  
 Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.  
  
 [ICorProfilerCallback4 (interfaz)](icorprofilercallback4-interface.md)  
 Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.  
  
 [ICorProfilerCallback5 (interfaz)](icorprofilercallback5-interface.md)  
 Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.  
  
 [ICorProfilerCallback6 (interfaz)](icorprofilercallback6-interface.md)  
 Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.  
  
 [ICorProfilerCallback7 (interfaz)](icorprofilercallback7-interface.md)  
 Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.  

[ICorProfilerCallback8 (interfaz)](icorprofilercallback8-interface.md)  
Proporciona métodos de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.

[ICorProfilerCallback9 (interfaz)](icorprofilercallback9-interface.md)  
Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha recopilado un método dinámico y que posteriormente se ha descargado.

 [ICorProfilerFunctionControl (interfaz)](icorprofilerfunctioncontrol-interface.md)  
 Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.  
  
 [ICorProfilerFunctionEnum (interfaz)](icorprofilerfunctionenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.  
  
 [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.  
  
 [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)  
 Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.  
  
 [ICorProfilerInfo3 (interfaz)](icorprofilerinfo3-interface.md)  
 Extiende la interfaz de `ICorProfilerInfo2` con métodos admitidos en el .NET Framework 4 y versiones posteriores.  
  
 [ICorProfilerInfo4 (interfaz)](icorprofilerinfo4-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.  
  
 [ICorProfilerInfo5 (interfaz)](icorprofilerinfo5-interface.md)  
 Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.  
  
 [ICorProfilerInfo6 (interfaz)](icorprofilerinfo6-interface.md)  
 Proporciona un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.  
  
 [ICorProfilerInfo7 (interfaz)](icorprofilerinfo7-interface.md)  
 Proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.  
  
 [ICorProfilerModuleEnum (interfaz)](icorprofilermoduleenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.  
  
 [ICorProfilerObjectEnum (interfaz)](icorprofilerobjectenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen. exe (generador de imágenes nativas)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
 [ICorProfilerThreadEnum (interfaz)](icorprofilerthreadenum-interface.md)  
 Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.  
  
 [IMethodMalloc (interfaz)](imethodmalloc-interface.md)  
 Proporciona el método de [asignación](imethodmalloc-alloc-method.md) para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Información general sobre la generación de perfiles](profiling-overview.md)  
  
 [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)  
  
 [Enumeraciones para generación de perfiles](profiling-enumerations.md)  
  
 [Estructuras para generación de perfiles](profiling-structures.md)
