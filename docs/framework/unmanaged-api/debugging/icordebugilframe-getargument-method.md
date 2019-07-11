---
title: ICorDebugILFrame::GetArgument (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e9f627f1ba213f663f042d1107afd1eb05b56b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757863"
---
# <a name="icordebugilframegetargument-method"></a>ICorDebugILFrame::GetArgument (Método)
Obtiene el valor del argumento especificado en este marco de pila del lenguaje intermedio (MSIL) de Microsoft.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwIndex`  
 [in] El índice del argumento en este marco de pila MSIL.  
  
 `ppValue`  
 [out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.  
  
## <a name="remarks"></a>Comentarios  
 El `GetArgument` método puede utilizarse en un marco de pila MSIL o en un marco compilado just-in-time (JIT).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
