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
ms.openlocfilehash: bcf5c5c9044a30fc8259dbc54bad8f3141f0f926
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733118"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>ICorProfilerCallback::ModuleAttachedToAssembly (Método)

Notifica al generador de perfiles que se está asociando un módulo a su ensamblado primario.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleId`  
 de IDENTIFICADOR del módulo que se va a adjuntar.  
  
 `AssemblyId`  
 de IDENTIFICADOR del ensamblado primario al que está asociado el módulo.  
  
## <a name="remarks"></a>Comentarios  

 Un módulo se puede cargar a través de una tabla de direcciones de importación (IAT), a través de una llamada a `LoadLibrary` o a través de una referencia de metadatos. Como resultado, el cargador de Common Language Runtime (CLR) tiene varias rutas de acceso de código para determinar el ensamblado en el que reside un módulo. Por lo tanto, es posible que después de llamar a [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , el módulo no sepa en qué ensamblado se encuentra y que no sea posible obtener el identificador del ensamblado primario. `ModuleAttachedToAssembly`Se llama al método cuando el módulo se adjunta a su ensamblado primario y se puede obtener el identificador del ensamblado primario.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
