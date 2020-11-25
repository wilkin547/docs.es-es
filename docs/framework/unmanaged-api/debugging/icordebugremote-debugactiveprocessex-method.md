---
title: ICorDebugRemote::DebugActiveProcessEx (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
ms.openlocfilehash: c9847fd6122aa32c95aecd5643a62a6775ae38d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712123"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>ICorDebugRemote::DebugActiveProcessEx (Método)

Inicia un proceso en un equipo remoto en el depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pRemoteTarget`  
 de Puntero a una [interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md). Este parámetro se usa para determinar el equipo en el que se está ejecutando el proceso.  
  
 `id`  
 de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.  
  
 `win32Attach`  
 [in] `true` Si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; en caso contrario, `false` .  
  
 `ppProcess`  
 enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK  
 Se adjuntó correctamente al proceso en el equipo remoto.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede asociar al proceso en el equipo remoto.  
  
## <a name="remarks"></a>Comentarios  

 En Silverlight no se admite la depuración en modo mixto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugRemote (Interfaz)](icordebugremote-interface.md)
- [ICorDebug (Interfaz)](icordebug-interface.md)

- [Interfaces para depuración](debugging-interfaces.md)
