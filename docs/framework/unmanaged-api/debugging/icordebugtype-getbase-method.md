---
description: 'Más información acerca de: ICorDebugType:: GetBase (método)'
title: ICorDebugType::GetBase (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: 78cd540974b540b704e946f6c723214d72e89ab4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658391"
---
# <a name="icordebugtypegetbase-method"></a>ICorDebugType::GetBase (Método)

Obtiene un puntero de interfaz a una ICorDebugType que representa el tipo base, si existe, del tipo representado por este `ICorDebugType` .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pBase`  
 enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el tipo base.  
  
## <a name="remarks"></a>Observaciones  

 Buscar el tipo base de un tipo es útil para implementar la funcionalidad común del depurador, como la impresión de todos los campos de un objeto o de sus clases primarias.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
