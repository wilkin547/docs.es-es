---
title: puntero a la función FExecuteInAppDomainCallback
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c3cafe3a8912702a093f9df7234112c0057b440
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431305"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a>puntero a la función FExecuteInAppDomainCallback
Señala a una función que llama a common language runtime (CLR) para ejecutar código administrado.  
  
 Este puntero de función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cookie`  
 [in] Un puntero a la memoria asignada por el llamador opaco que contiene el código administrado que se ejecuta.  
  
 La asignación y duración de esta memoria se controlan por el llamador (es decir, el CLR). Esto no es memoria del montón administrado de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorWks.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
