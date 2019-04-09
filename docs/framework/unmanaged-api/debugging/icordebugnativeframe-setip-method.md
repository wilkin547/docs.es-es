---
title: ICorDebugNativeFrame::SetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 604486a074c3dbe3d19b741df28499ee03e1b2e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193283"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP (Método)
Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `nOffset`  
 [in] La ubicación de desplazamiento en el código nativo.  
  
## <a name="remarks"></a>Comentarios  
 Las llamadas a `SetIP` invalidar inmediatamente todos los marcos y cadenas para el subproceso actual. Si el depurador necesita información de marco después de llamar a `SetIP`, que debe realizar un seguimiento de pila nuevo.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) intentará mantener el marco de pila en un estado válido. Sin embargo, incluso si el marco está en un estado válido, lo que se refiere el tiempo de ejecución, todavía puede haber problemas, como variables locales sin inicializar y así sucesivamente. El llamador es responsable de garantizar la coherencia del programa en ejecución.  
  
 En las plataformas de 64 bits, no se puede mover el puntero de instrucción fuera de un `catch` o `finally` bloque. Si `SetIP` se llama para hacer ese cambio en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
