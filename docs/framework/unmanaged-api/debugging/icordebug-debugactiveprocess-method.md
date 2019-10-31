---
title: ICorDebug::DebugActiveProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 5b988b110100cd159b8e262573df409847d635c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134123"
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess (Método)
Asocia el depurador a un proceso existente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.  
  
 `win32Attach`  
 de Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; de lo contrario, `false`.  
  
 `ppProcess`  
 enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.  
  
## <a name="remarks"></a>Comentarios  
 No se admite la depuración de interoperabilidad en las plataformas Win9x y no x86, como las plataformas basadas en IA-64 y AMD64.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
