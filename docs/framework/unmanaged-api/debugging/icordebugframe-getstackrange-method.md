---
title: ICorDebugFrame::GetStackRange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9f58e66286f5e3e169507efd2f87ce10e9d323b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754857"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange (Método)
Obtiene el intervalo de direcciones absolutas de este marco de pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pStart`  
 [out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección inicial del marco de pila representado por este `ICorDebugFrame` objeto.  
  
 `pEnd`  
 [out] Un puntero a un `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este `ICorDebugFrame` objeto.  
  
## <a name="remarks"></a>Comentarios  
 El intervalo de direcciones de la pila es útil para juntar los seguimientos de pila intercalados recopilados de varios motores de depuración. El intervalo numérico no proporciona información sobre el contenido del marco de pila. Es significativo únicamente para la comparación de las ubicaciones del marco de pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
