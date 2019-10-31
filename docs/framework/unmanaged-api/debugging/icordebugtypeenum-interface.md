---
title: ICorDebugTypeEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum
helpviewer_keywords:
- ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: 159ccfcf-b37c-4ad9-8e0d-a9a443262472
topic_type:
- apiref
ms.openlocfilehash: a8fa4f2fbe576083658a934e30177bb7a48be06d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110228"
---
# <a name="icordebugtypeenum-interface"></a>ICorDebugTypeEnum (Interfaz)
Implementa los métodos "ICorDebugEnum" y enumera las matrices "ICorDebugType".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-next-method.md)|Obtiene el número especificado de instancias de `ICorDebugType` de la enumeración, comenzando en la posición actual.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
