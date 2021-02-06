---
description: 'Más información acerca de: ICorProfilerInfo:: Gethandlefromthread ((método)'
title: ICorProfilerInfo::GetHandleFromThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
ms.openlocfilehash: 541a2872bc3cbbe8233e09283b9773957b0a7daf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647562"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a>ICorProfilerInfo::GetHandleFromThread (Método)

Asigna el identificador de un subproceso a un identificador de subproceso de Win32.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a>Parámetros  

 `threadId`  
 de IDENTIFICADOR del subproceso que se va a asignar.  
  
 `phThread`  
 enuncia Puntero a un identificador de subproceso de Win32.  
  
## <a name="remarks"></a>Observaciones  

 El generador de perfiles debe llamar a la `DuplicateHandle` función de Win32 en el identificador antes de usarlo.  

 El identificador devuelto por este método es propiedad del tiempo de ejecución y el generador de perfiles nunca debe cerrarlo.
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
