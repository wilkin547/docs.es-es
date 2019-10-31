---
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
ms.openlocfilehash: c5d6cfa3826667514eb70f9bb0df118d9ba0d07c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127818"
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
  
## <a name="remarks"></a>Comentarios  
 El subproceso especificado no podrá ejecutar código administrado ni entrar en el tiempo de ejecución de ninguna manera. Un ejemplo de este tipo de subproceso sería un subproceso en proceso para admitir depuradores de script heredados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorConfiguration (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
