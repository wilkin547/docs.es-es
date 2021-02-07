---
description: 'Más información sobre: ICorDebugDataTarget:: GetThreadContext (método)'
title: ICorDebugDataTarget::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: cf40579aa0a495af4e5e775334d177ca6f3da86f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710639"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>ICorDebugDataTarget::GetThreadContext (Método)

Devuelve el contexto del subproceso actual para el subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwThreadID`  
 de Identificador del subproceso cuyo contexto se va a recuperar. El identificador está definido por el sistema operativo.  
  
 `contextFlags`  
 de Combinación bit a bit de las marcas dependientes de la plataforma que indican qué partes del contexto se deben leer.  
  
 `contextSize`  
 [in] Tamaño de `pContext`.  
  
 `pContext`  
 enuncia Búfer donde se almacenará el contexto del subproceso.  
  
## <a name="remarks"></a>Observaciones  

 En las plataformas de Windows, `pContext` debe ser una `CONTEXT` estructura (definida en Winnt. h) que sea adecuada para el tipo de equipo especificado por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) . `contextFlags` debe tener los mismos valores que el `ContextFlags` campo de la `CONTEXT` estructura. La `CONTEXT` estructura es específica del procesador; Consulte el archivo winnt. h para obtener más información.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugDataTarget (Interfaz)](icordebugdatatarget-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
