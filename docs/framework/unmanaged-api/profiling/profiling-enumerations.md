---
title: Enumeraciones para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: bc90743fb348c31bd2f7487c1573ec38a43bd3af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447448"
---
# <a name="profiling-enumerations"></a>Enumeraciones para generación de perfiles
En esta sección se describen las enumeraciones no administradas que utiliza la API de generación de perfiles.  
  
## <a name="in-this-section"></a>Esta sección  
 [COR_PRF_CLAUSE_TYPE (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.  
  
 [COR_PRF_CODEGEN_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 Define las marcas de generación de código que se pueden establecer con el método [ICorProfilerFunctionControl:: setcodegenflags (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) .  
  
 [COR_PRF_FINALIZER_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 Describe el finalizador de un objeto.  
  
 [COR_PRF_GC_GENERATION (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 Identifica la generación de una recolección de elementos no utilizados.  
  
 [COR_PRF_GC_REASON (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.  
  
 [COR_PRF_GC_ROOT_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 Indica las propiedades de la raíz de un recolector de elementos no utilizados.  
  
 [COR_PRF_GC_ROOT_KIND (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 Indica el tipo de raíz del recolector de elementos no utilizados expuesta por la devolución de llamada [ICorProfilerCallback2:: RootReferences2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) .  
  
 [COR_PRF_HIGH_MONITOR (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 Proporciona marcas además de las que se encuentran en la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) que el generador de perfiles puede especificar para el método [ICorProfilerInfo5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) cuando se está cargando.  
  
 [COR_PRF_JIT_CACHE (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 Indica el resultado de una búsqueda de función en caché.  
  
 [COR_PRF_MISC (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 Contiene valores constantes que especifican identificadores especiales.  
  
 [COR_PRF_MODULE_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 Especifica las propiedades de un módulo.  
  
 [COR_PRF_MONITOR (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.  
  
 [COR_PRF_RUNTIME_TYPE (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 Contiene valores que indican la versión de Common Language Runtime.  
  
 [COR_PRF_SNAPSHOT_INFO (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 Especifica cuántos datos se devolverán con una instantánea de pila en cada llamada a la función `StackSnapshotCallback` del generador de perfiles.  
  
 [COR_PRF_STATIC_TYPE (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.  
  
 [COR_PRF_SUSPEND_REASON (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 Indica el motivo por el que el tiempo de ejecución se suspendió.  
  
 [COR_PRF_TRANSITION_REASON (enumeración)](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Información general sobre la generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [Estructuras para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
