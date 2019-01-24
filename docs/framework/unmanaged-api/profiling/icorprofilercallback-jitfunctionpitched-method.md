---
title: ICorProfilerCallback::JITFunctionPitched (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91bc626e2c75cd7eb2eafad0fc26d343e5b278e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530737"
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
 [in] El identificador de la función que se ha quitado.  
  
## <a name="remarks"></a>Comentarios  
 Si se llama a la función quitada, el generador de perfiles recibirá nuevos eventos de compilación JIT cuando se vuelve a compilar la función. Actualmente, el compilador JIT de common language runtime (CLR) no quita las funciones de la memoria, por lo que esta devolución de llamada no se utiliza actualmente y no se recibirán el generador de perfiles.  
  
 El valor de `functionId` no es válido hasta que se vuelve a compilar la función. Cuando se vuelve a compilar la función, el mismo `functionId` se usará el valor.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
