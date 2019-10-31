---
title: GetCLRIdentityManager (Función)
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 3c6def32c63e3557a4de72baf7b1c3e67feb4891
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136527"
---
# <a name="getclridentitymanager-function"></a>GetCLRIdentityManager (Función)
Obtiene un puntero a una interfaz que permite al Common Language Runtime (CLR) administrar las identidades.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `riid`  
 de `REFIID` (identificador de interfaz) que especifica la interfaz que se va a obtener. Este valor debe ser IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.  
  
 `ppManager`  
 enuncia Puntero a la dirección de un objeto [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) .  
  
## <a name="remarks"></a>Comentarios  
 Llame a la función [GetRealProcAddress (](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) para obtener un puntero a la función `GetCLRIdentityManager`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorWks. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
