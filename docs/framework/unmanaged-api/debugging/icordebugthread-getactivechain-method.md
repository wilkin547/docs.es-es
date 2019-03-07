---
title: ICorDebugThread::GetActiveChain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05f5a3f29c7b72ed83c1456175f68ef9b986e3e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483321"
---
# <a name="icordebugthreadgetactivechain-method"></a>ICorDebugThread::GetActiveChain (Método)
Obtiene un puntero de interfaz a la cadena de pila activa (más reciente) en este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppChain`  
 [out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de la pila.  
  
## <a name="remarks"></a>Comentarios  
 El `ppChain` parámetro es null si ninguna cadena de la pila está activa actualmente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
