---
title: IManagedObject::GetObjectIdentity (Método)
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
ms.openlocfilehash: 8c884569a452fb2985713956f942205cda6ea1ff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141252"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>IManagedObject::GetObjectIdentity (Método)
Obtiene la identidad de este objeto administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pBSTRGUID`  
 enuncia Puntero al GUID del proceso en el que reside el objeto.  
  
 `AppDomainID`  
 enuncia Puntero al identificador del dominio de aplicación del objeto.  
  
 `pCCW`  
 enuncia Puntero al índice de un objeto en la tabla v clásica de COM.  
  
## <a name="remarks"></a>Comentarios  
 La identidad de un objeto administrado incluye el GUID del proceso, el identificador del dominio de aplicación y el índice del objeto en la tabla v clásica de COM.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IManagedObject (interfaz)](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
