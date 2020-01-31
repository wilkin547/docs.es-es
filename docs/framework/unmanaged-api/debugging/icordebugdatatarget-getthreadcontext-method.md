---
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
ms.openlocfilehash: 3eace2d91b3bb6e637a659b8b49a31450ebc2c42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783728"
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
  
## <a name="parameters"></a>Parameters  
 `dwThreadID`  
 de Identificador del subproceso cuyo contexto se va a recuperar. El identificador está definido por el sistema operativo.  
  
 `contextFlags`  
 de Combinación bit a bit de las marcas dependientes de la plataforma que indican qué partes del contexto se deben leer.  
  
 `contextSize`  
 [in] Tamaño de `pContext`.  
  
 `pContext`  
 enuncia Búfer donde se almacenará el contexto del subproceso.  
  
## <a name="remarks"></a>Notas  
 En las plataformas de Windows, `pContext` debe ser una estructura de `CONTEXT` (definida en Winnt. h) que sea adecuada para el tipo de equipo especificado por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) . `contextFlags` deben tener los mismos valores que el campo `ContextFlags` de la estructura `CONTEXT`. La estructura de `CONTEXT` es específica del procesador; Consulte el archivo winnt. h para obtener más información.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugDataTarget (interfaz)](icordebugdatatarget-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
