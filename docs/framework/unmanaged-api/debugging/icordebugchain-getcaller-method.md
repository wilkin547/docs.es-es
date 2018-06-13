---
title: ICorDebugChain::GetCaller (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0b5d702e9718ce6ac537beae67fc190b152b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405148"
---
# <a name="icordebugchaingetcaller-method"></a>ICorDebugChain::GetCaller (Método)
Obtiene la cadena que ha llamado a esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppChain`  
 [out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.  
  
 Si esta cadena se llamó espontáneamente (como ocurriría si esta cadena o el depurador inicializara la pila de llamadas), `ppChain` será null.  
  
## <a name="remarks"></a>Comentarios  
 La cadena de llamada puede estar en un subproceso diferente, si se calculan las referencias de la llamada entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
