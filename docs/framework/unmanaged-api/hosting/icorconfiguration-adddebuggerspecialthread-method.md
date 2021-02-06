---
description: 'Más información sobre: ICorConfiguration:: Adddebuggerspecialthread ((método)'
title: ICorConfiguration::AddDebuggerSpecialThread (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
ms.openlocfilehash: b6904c2e4d5c265244ac096e0d64c2fc7f5d1be5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636720"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>ICorConfiguration::AddDebuggerSpecialThread (Método)

Indica a los servicios de depuración que se debe permitir que un subproceso determinado se siga ejecutando mientras el depurador tiene una aplicación detenida durante escenarios de depuración administrados o no administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwSpecialThreadId`  
 de IDENTIFICADOR del subproceso al que se debe permitir que continúe la ejecución.  
  
## <a name="remarks"></a>Observaciones  

 El subproceso especificado no podrá ejecutar código administrado ni entrar en el tiempo de ejecución de ninguna manera. Un ejemplo de este tipo de subproceso sería un subproceso en proceso para admitir depuradores de script heredados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorConfiguration (Interfaz)](icorconfiguration-interface.md)
