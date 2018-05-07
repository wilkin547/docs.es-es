---
title: ICorProfilerCallback::ExceptionThrown (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3358150754fd039d6e6107efd61c8d950fd02f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackexceptionthrown-method"></a>ICorProfilerCallback::ExceptionThrown (Método)
Notifica al generador de perfiles que se ha producido una excepción.  
  
> [!NOTE]
>  Esta función se invoca únicamente si la excepción alcanza el código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `thrownObjectId`  
 [in] El identificador del objeto que provocó la excepción.  
  
## <a name="remarks"></a>Comentarios  
 El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente. Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.  
  
 Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
