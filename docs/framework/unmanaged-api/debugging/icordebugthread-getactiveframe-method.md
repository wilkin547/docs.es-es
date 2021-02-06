---
description: 'Más información acerca de: ICorDebugThread:: GetActiveFrame ((método)'
title: ICorDebugThread::GetActiveFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: 3b15aad39503dfec9ac8f98f839ee1a6b16b3f90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659267"
---
# <a name="icordebugthreadgetactiveframe-method"></a>ICorDebugThread::GetActiveFrame (Método)

Obtiene un puntero de interfaz al marco activo (más reciente) en este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppFrame`  
 enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFrame que representa un marco.  
  
## <a name="remarks"></a>Observaciones  

 El `ppFrame` parámetro es NULL si no hay ningún marco activo actualmente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
