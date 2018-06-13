---
title: IAppDomainBinding::OnAppDomain (Método)
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5db040f6db078b211043c547eed823c9b495ac97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431327"
---
# <a name="iappdomainbindingonappdomain-method"></a>IAppDomainBinding::OnAppDomain (Método)
Llamado por common language runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAppdomain`  
 [in] Un puntero a un [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) objeto de interfaz que representa el nuevo dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IAppDomainBinding (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
