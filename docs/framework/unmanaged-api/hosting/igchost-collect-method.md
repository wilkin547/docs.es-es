---
title: IGCHost::Collect (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bce005a677dcb74c176a6dddfb2726f6b1fd0e8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436912"
---
# <a name="igchostcollect-method"></a>IGCHost::Collect (Método)
Fuerza una recolección que se produzca la generación determinada, con independencia del estado de la colección de elementos no utilizados actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Generation`  
 [in] La generación en la que se va a realizar la recolección de elementos. Un valor de -1 indica que todas las generaciones se someterán a una colección de elementos no utilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost.idl, GCHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IGCHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
