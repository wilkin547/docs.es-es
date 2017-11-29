---
title: "ICorProfilerCallback::JITFunctionPitched (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITFunctionPitched
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a5b14bc5735c83897e818ca2038455e0c6510e27
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched (Método)
Notifica al generador de perfiles que una función que ha sido just-in-time (JIT)-compilado se ha quitado de la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función que se quitó.  
  
## <a name="remarks"></a>Comentarios  
 Si se llama a la función quitada, el generador de perfiles recibirá nuevos eventos de compilación JIT cuando se vuelve a compilar la función. Actualmente, el compilador JIT de common language runtime (CLR) no quita funciones de la memoria, por lo que esta devolución de llamada no se utiliza actualmente y no se recibirán el generador de perfiles.  
  
 El valor de `functionId` no es válido hasta que se vuelve a compilar la función. Cuando se vuelve a compilar la función, el mismo `functionId` se usará el valor.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
