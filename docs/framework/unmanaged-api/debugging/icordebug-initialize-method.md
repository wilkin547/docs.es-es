---
description: 'Más información acerca de: ICorDebug:: Initialize (método)'
title: ICorDebug::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
ms.openlocfilehash: 6b6ddd8c1c21470477420909bcf75906b5731ee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791600"
---
# <a name="icordebuginitialize-method"></a>ICorDebug::Initialize (Método)

Inicializa el objeto `ICorDebug`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a>Observaciones  

 El depurador debe llamar a `Initialize` en el momento de la creación para inicializar los servicios de depuración. Se debe llamar a este método antes de llamar a cualquier otro método en `ICorDebug` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](icordebug-interface.md)
