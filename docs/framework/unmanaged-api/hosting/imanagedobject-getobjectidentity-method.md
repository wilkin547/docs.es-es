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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1975e5bf20453a3bcd6761d9734be7ddd2ceef7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imanagedobjectgetobjectidentity-method"></a>IManagedObject::GetObjectIdentity (Método)
Obtiene la identidad de este objeto administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pBSTRGUID`  
 [out] Un puntero al GUID del proceso en el que reside el objeto.  
  
 `AppDomainID`  
 [out] Un puntero al identificador del objeto dominio de aplicación.  
  
 `pCCW`  
 [out] Puntero al índice del objeto en COM clásico v-table.  
  
## <a name="remarks"></a>Comentarios  
 La identidad de un objeto administrado incluye el GUID de proceso, Id. de dominio de aplicación y el índice del objeto en COM clásico v-table.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IManagedObject (interfaz)](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
