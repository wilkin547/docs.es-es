---
description: 'Más información sobre: ICorDebugChain:: GetCaller ((método)'
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
ms.openlocfilehash: 5af2132b7fec9e70704db980b95221db6eb273f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695026"
---
# <a name="icordebugchaingetcaller-method"></a>ICorDebugChain::GetCaller (Método)

Obtiene la cadena que llamó a esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppChain`  
 enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.  
  
 Si se llamó a esta cadena espontáneamente (como sería el caso si esta cadena o el depurador inicializara la pila de llamadas), `ppChain` será null.  
  
## <a name="remarks"></a>Observaciones  

 La cadena de llamada puede estar en un subproceso diferente, si se serializó la llamada entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
