---
description: 'Más información sobre: ICorDebugChain:: Getcallee ((método)'
title: ICorDebugChain::GetCallee (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: 4787893c86804c648dae14bf2e6f7425808104b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661433"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee (Método)

Obtiene la cadena a la que llamó esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppChain`  
 enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena a la que se ha llamado. Si esta cadena se está ejecutando actualmente (es decir, si esta cadena no está esperando a que devuelva una cadena llamada), `ppChain` será null.  
  
## <a name="remarks"></a>Observaciones  

 Esta cadena esperará a que se devuelva la cadena llamada antes de reanudar la ejecución. La cadena llamada puede estar en otro subproceso en el caso de las llamadas de serialización entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
