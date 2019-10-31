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
ms.openlocfilehash: 828e4dc67cb93d0a35879e94b54c9fac6e5bda16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124081"
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
 enuncia Puntero a un `CORDB_ADDRESS` que especifica la dirección inicial del marco de pila representado por este objeto `ICorDebugFrame`.  
  
 `pEnd`  
 enuncia Puntero a un `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este objeto `ICorDebugFrame`.  
  
## <a name="remarks"></a>Comentarios  
 El intervalo de direcciones de la pila es útil para juntar juntos los seguimientos de la pila intercalados recopilados de varios motores de depuración. El intervalo numérico no proporciona información sobre el contenido del marco de pila. Solo es significativo para la comparación de las ubicaciones de los marcos de pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
