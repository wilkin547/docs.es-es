---
title: ICorProfilerCallback::ExceptionCLRCatcherFound (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: ef5122d49c428af4faa27f3827a5c60721ef0f74
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435831"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a>ICorProfilerCallback::ExceptionCLRCatcherFound (Método)
Llamado cuando se encuentra un bloque `catch` para una excepción dentro del propio Common Language Runtime (CLR). Este método está obsoleto en la .NET Framework versión 2,0.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versión de .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ExceptionCLRCatcherExecute (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
