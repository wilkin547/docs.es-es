---
title: CorBindToRuntimeByCfg (Función)
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 3802354bf52cd2aab2a4149d565993b9965e8312
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138302"
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg (Función)
Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión que se lee de un archivo XML.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pCfgStream`  
 de Un puntero a un objeto `IStream` que lee el archivo XML.  
  
 `reserved`  
 de Reservado para uso futuro. Use 0 (cero) como valor.  
  
 `startupFlags`  
 de Un valor de la enumeración [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) que especifica el comportamiento de inicio de CLR.  
  
 `rclsid`  
 de `CLSID` de la coclase que implementa la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) . Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 de `IID` del `ICorRuntimeHost` o de la interfaz de `ICLRRuntimeHost`. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 enuncia Puntero a la dirección de la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar. Para obtener más información acerca de los archivos XML, vea [esquema del archivo de configuración](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorBindToCurrentRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
