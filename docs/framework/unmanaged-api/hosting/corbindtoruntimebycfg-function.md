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
ms.openlocfilehash: 9326484c6a9f96d245e3c61a0ac3e3465a8a6dcd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616650"
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
 de Un puntero a un `IStream` objeto que lee el archivo XML.  
  
 `reserved`  
 [in] Reservado para uso futuro. Use 0 (cero) como valor.  
  
 `startupFlags`  
 de Un valor de la enumeración [STARTUP_FLAGS](startup-flags-enumeration.md) que especifica el comportamiento de inicio de CLR.  
  
 `rclsid`  
 de `CLSID`De la coclase que implementa la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 de `IID`De la `ICorRuntimeHost` `ICLRRuntimeHost` interfaz o. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 enuncia Puntero a la dirección de la interfaz devuelta.  
  
## <a name="remarks"></a>Observaciones  
 El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar. Para obtener más información acerca de los archivos XML, vea [esquema del archivo de configuración](../../configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [CorBindToCurrentRuntime (Función)](corbindtocurrentruntime-function.md)
- [CorBindToRuntime (Función)](corbindtoruntime-function.md)
- [CorBindToRuntimeEx (Función)](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost (Función)](corbindtoruntimehost-function.md)
- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
