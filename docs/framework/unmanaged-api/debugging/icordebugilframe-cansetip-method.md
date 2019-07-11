---
title: ICorDebugILFrame::CanSetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75b28dafae2861a2d33363f95a46bf1abf4cda35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756581"
---
# <a name="icordebugilframecansetip-method"></a>ICorDebugILFrame::CanSetIP (Método)
Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en el código de lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `nOffset`  
 [in] El valor deseado para el puntero de instrucción.  
  
## <a name="remarks"></a>Comentarios  
 Use la `CanSetIP` método antes de llamar a la [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) método. Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía se puede llamar `ICorDebugILFrame::SetIP`, pero no hay ninguna garantía de que el depurador continuará la ejecución correcta y segura del código que se está depurando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, [Cordebug], h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
