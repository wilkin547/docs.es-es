---
title: "ICorDebugNativeFrame::SetIP (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.SetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25b4f42eb6f10ecade468824d9d790a2bce740a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP (Método)
Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `nOffset`  
 [in] La ubicación de desplazamiento en el código nativo.  
  
## <a name="remarks"></a>Comentarios  
 Las llamadas a `SetIP` inmediatamente invalidar todos los marcos y cadenas para el subproceso actual. Si el depurador necesita información del marco después de llamar a `SetIP`, debe realizar un seguimiento de pila nueva.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) intentará mantener el marco de pila en un estado válido. Sin embargo, incluso si el marco está en un estado válido, tal y como lo que se refiere el tiempo de ejecución, todavía puede haber problemas, como variables locales sin inicializar y así sucesivamente. El llamador es responsable de garantizar la coherencia del programa en ejecución.  
  
 En plataformas de 64 bits, no se puede mover el puntero de instrucción fuera de un `catch` o `finally` bloque. Si `SetIP` se llama para hacer ese cambio en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 
