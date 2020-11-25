---
title: ICorDebugILFrame::SetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
ms.openlocfilehash: fdc3d96fd5ad9a6ff59b863cd3f0450283ea0146
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721379"
---
# <a name="icordebugilframesetip-method"></a>ICorDebugILFrame::SetIP (Método)

Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código del lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `nOffset`  
 Ubicación de desplazamiento en el código MSIL.  
  
## <a name="remarks"></a>Comentarios  

 Llama a para `SetIP` invalidar inmediatamente todos los marcos y cadenas del subproceso actual. Si el depurador necesita información de fotogramas después de una llamada a `SetIP` , debe realizar un nuevo seguimiento de la pila.  
  
 [ICorDebug](icordebug-interface.md) intentará mantener el marco de pila en un estado válido. Sin embargo, aunque el marco esté en un estado válido, puede haber problemas como las variables locales sin inicializar. El autor de la llamada es responsable de garantizar la coherencia del programa en ejecución.  
  
 En las plataformas de 64 bits, el puntero de instrucción no se puede sacar de un `catch` `finally` bloque o. Si `SetIP` se llama a para hacer este tipo de movimiento en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
