---
title: ComCallUnmarshal (Coclase)
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
ms.openlocfilehash: 38f3140a181deae1a86569bfc2eb7cf3cd7d1991
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131928"
---
# <a name="comcallunmarshal-coclass"></a>ComCallUnmarshal (Coclase)
Proporciona interfaces para administrar el cálculo de referencias de punteros de interfaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a>Interfaces  
  
|Interfaz|Descripción|  
|---------------|-----------------|  
|`IMarshal`|Proporciona métodos para crear, inicializar y administrar un proxy en un proceso de cliente.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Coclases para el hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
