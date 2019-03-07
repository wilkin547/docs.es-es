---
title: ICorProfilerCallback::AssemblyLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bb5586271c252879b503dd093c88380197d5bce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479732"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>ICorProfilerCallback::AssemblyLoadFinished (Método)
Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Parámetros  
 `assemblyId`  
 [in] Identifica el ensamblado que se cargó.  
  
 `hrStatus`  
 [in] Un HRESULT que indica si el ensamblado terminó de cargar correctamente.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `assemblyId` no es válido para una solicitud de información hasta que el `AssemblyLoadFinished` se llama al método.  
  
 Algunas partes de la carga del ensamblado podrían continuar después de la `AssemblyLoadFinished` devolución de llamada. Un error HRESULT en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la carga el ensamblado se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
