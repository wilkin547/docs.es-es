---
description: 'Más información acerca de: ICorDebugNativeFrame:: SetIP (método)'
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
ms.openlocfilehash: cb55b35eb4bd107a7273fd80ba83baac96610fb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729177"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP (Método)

Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `nOffset`  
 de Ubicación de desplazamiento en el código nativo.  
  
## <a name="remarks"></a>Observaciones  

 Llama a para `SetIP` invalidar inmediatamente todos los marcos y cadenas del subproceso actual. Si el depurador necesita información de fotogramas después de una llamada a `SetIP` , debe realizar un nuevo seguimiento de la pila.  
  
 [ICorDebug](icordebug-interface.md) intentará mantener el marco de pila en un estado válido. Sin embargo, aunque el marco esté en un estado válido, en lo que se refiere al tiempo de ejecución, todavía puede haber problemas, como variables locales sin inicializar, etc. El autor de la llamada es responsable de garantizar la coherencia del programa en ejecución.  
  
 En las plataformas de 64 bits, el puntero de instrucción no se puede sacar de un `catch` `finally` bloque o. Si `SetIP` se llama a para hacer este tipo de movimiento en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
