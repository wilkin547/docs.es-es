---
description: 'Más información sobre: ICorDebugFrame:: Createstepper ((método)'
title: ICorDebugFrame::CreateStepper (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 394418b89fd7a1c780a5bc33b97b8ef40bab8df2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693101"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper (Método)

Obtiene un stepper que permite al depurador realizar operaciones de ejecución de paso en relación con este ICorDebugFrame.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppStepper`  
 enuncia Puntero a la dirección de un objeto ICorDebugStepper que permite al depurador realizar operaciones de ejecución de paso en relación con el marco actual.  
  
## <a name="remarks"></a>Observaciones  

 Si el marco no está activo, el objeto stepper normalmente tendrá que volver al marco antes de que se complete el paso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
