---
description: 'Más información sobre: ICorConfiguration:: Setgchostcontrol ((método)'
title: ICorConfiguration::SetGCHostControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: 4d3d6e5e5275adf02f9d693234a5c8e77714fd03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636655"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a>ICorConfiguration::SetGCHostControl (Método)

Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pGCHostControl`  
 de Un puntero a un objeto [igchostcontrol (](igchostcontrol-interface.md) que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorConfiguration (Interfaz)](icorconfiguration-interface.md)
