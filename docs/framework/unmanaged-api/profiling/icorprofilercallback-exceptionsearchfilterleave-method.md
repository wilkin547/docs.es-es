---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionsearchfilterleave ((método)'
title: ICorProfilerCallback::ExceptionSearchFilterLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
ms.openlocfilehash: d2195e8e055b25f71efbfbcc71e933daa07a4e3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799127"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a>ICorProfilerCallback::ExceptionSearchFilterLeave (Método)

Notifica al generador de perfiles que un filtro de usuario ha terminado de ejecutarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)
