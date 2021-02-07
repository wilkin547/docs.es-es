---
description: 'Más información acerca de: interfaz ICorDebugAppDomainEnum ('
title: Interfaz ICorDebugAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: dfea6254e6cf4f162e44d057fb4126a67a087b61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754165"
---
# <a name="icordebugappdomainenum-interface"></a>Interfaz ICorDebugAppDomainEnum

Proporciona el `Next` método, que devuelve un número especificado de `ICorDebugAppDomainEnum` valores a partir de la siguiente ubicación de la enumeración. Esta interfaz es una subclase de "ICorDebugEnum".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](icordebugappdomainenum-next-method.md)|Obtiene el número especificado de dominios de aplicación de la colección, comenzando en la posición actual del cursor.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](icordebug-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
