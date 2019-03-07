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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b3869c9f96eee6f0e3066a99a58a154a2f5f2ee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480096"
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess (Método)
Asocia al depurador a un proceso existente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 [in] El identificador del proceso al que va a adjuntar el depurador.  
  
 `win32Attach`  
 [in] Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; en caso contrario, `false`.  
  
 `ppProcess`  
 [out] Un puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha vinculado el depurador.  
  
## <a name="remarks"></a>Comentarios  
 No se admite la depuración de interoperabilidad en plataformas Win9x y no x86, como las plataformas basadas en IA-64 y basado en AMD64.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
