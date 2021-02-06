---
description: 'Más información sobre: ICorConfiguration:: Setdebuggerthreadcontrol ((método)'
title: ICorConfiguration::SetDebuggerThreadControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 9bf024f3feb6df44a94f8a5f1a626bb6e0c91d31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636668"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a>ICorConfiguration::SetDebuggerThreadControl (Método)

Establece la interfaz de devolución de llamada a la que los servicios de depuración llamarán como subprocesos Common Language Runtime (CLR) se bloquean y desbloquean para la depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pDebuggerThreadControl`  
 de Un puntero a un objeto [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) que notifica al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorConfiguration (Interfaz)](icorconfiguration-interface.md)
