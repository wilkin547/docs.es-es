---
description: 'Más información acerca de: interfaz ICorDebugAppDomain3'
title: ICorDebugAppDomain3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
ms.openlocfilehash: 6575aa685759102443babeaf82774e6221b80693
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772216"
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3 (Interfaz)

Proporciona métodos para recuperar información sobre las representaciones administradas de Windows Runtime tipos cargados actualmente en un dominio de aplicación. Esta interfaz es una extensión de las interfaces ICorDebugAppDomain e ICorDebugAppDomain2.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ICorDebugAppDomain3:: Getcachedwinrttypes (](icordebugappdomain3-getcachedwinrttypes-method.md)|Obtiene un enumerador para todos los tipos de Windows Runtime almacenados en caché.|  
|[ICorDebugAppDomain3:: Getcachedwinrttypesforiids (](icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Obtiene un enumerador para los tipos de Windows Runtime almacenados en memoria caché en un dominio de aplicación en función de sus identificadores de interfaz.|  
  
## <a name="remarks"></a>Observaciones  

 Esta interfaz está pensada para que la use un depurador junto con una llamada de evaluación de función a `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)` . Cuando el método recupera los identificadores de interfaz admitidos por un objeto de servidor Windows Runtime, el depurador puede usar los métodos definidos en esta interfaz para asignarlos a tipos administrados que corresponden a esas interfaces.  
  
 Para recuperar una instancia de esta interfaz, ejecute `QueryInterface` en una instancia de la interfaz ICorDebugAppDomain o ICorDebugAppDomain2.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Windows Runtime  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
