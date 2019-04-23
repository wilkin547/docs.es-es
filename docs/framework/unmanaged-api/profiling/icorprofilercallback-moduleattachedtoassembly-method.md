---
title: ICorProfilerCallback::ModuleAttachedToAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 791827b9c4b60cb2ee963881bc8e1a6131cd00fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139924"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>ICorProfilerCallback::ModuleAttachedToAssembly (Método)
Notifica al generador de perfiles que se va a adjuntar un módulo a su ensamblado principal.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo que se va a adjuntar.  
  
 `AssemblyId`  
 [in] El identificador del ensamblado primario al que está asociado el módulo.  
  
## <a name="remarks"></a>Comentarios  
 Un módulo se puede cargar a través de una tabla de direcciones de importación (IAT), mediante una llamada a `LoadLibrary`, o a través de una referencia de metadatos. Como resultado, el cargador de common language runtime (CLR) tiene varias rutas de acceso de código para determinar el ensamblado en el que reside un módulo. Por lo tanto, es posible que después [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) se llama, el módulo no sabe en qué ensamblado se encuentra en y no es posible obtener el identificador del ensamblado principal. El `ModuleAttachedToAssembly` se llama al método cuando el módulo se conecta a su ensamblado primario y su ensamblado primario identificador puede obtenerse.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
