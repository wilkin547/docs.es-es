---
description: 'Más información sobre: ICorConfiguration:: Setgcthreadcontrol ((método)'
title: ICorConfiguration::SetGCThreadControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 8b9388bdefb9da2ce51b62ab68eeee54645e43ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636649"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>ICorConfiguration::SetGCThreadControl (Método)

Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pGCThreadControl`  
 de Un puntero a un objeto [IGCThreadControl](igcthreadcontrol-interface.md) que notifica al host la suspensión de subprocesos para tareas que no son de tiempo de ejecución.  
  
## <a name="remarks"></a>Observaciones  

 El host puede elegir dentro de la devolución de llamada [IGCThreadControl:: ThreadIsBlockingForSuspension (](igcthreadcontrol-threadisblockingforsuspension-method.md) si se va a volver a programar un subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorConfiguration (Interfaz)](icorconfiguration-interface.md)
