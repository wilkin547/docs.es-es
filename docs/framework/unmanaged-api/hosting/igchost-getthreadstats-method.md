---
description: 'Más información sobre: IGCHost:: GetThreadStats ((método)'
title: IGCHost::GetThreadStats (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
ms.openlocfilehash: 2d923560e915a0c88035caad70ad91149d793cb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709664"
---
# <a name="igchostgetthreadstats-method"></a>IGCHost::GetThreadStats (Método)

Obtiene las estadísticas por subproceso para la recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pFiberCookie`  
 de Puntero a una cookie de fibra que especifica el subproceso para el que se van a recuperar las estadísticas.  
  
 `pStats`  
 [in, out] Puntero a una estructura de [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) que contiene las estadísticas de recolección de elementos no utilizados para el subproceso especificado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCHost (Interfaz)](igchost-interface.md)
