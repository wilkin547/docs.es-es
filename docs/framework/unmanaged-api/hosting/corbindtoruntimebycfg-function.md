---
description: 'Más información acerca de: CorBindToRuntimeByCfg (función)'
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
ms.openlocfilehash: c1acf6a8f1d8637bc2d6cd180016ff51cf500107
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790079"
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
 de `CLSID` De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 de `IID` De la `ICorRuntimeHost` `ICLRRuntimeHost` interfaz o. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 enuncia Puntero a la dirección de la interfaz devuelta.  
  
## <a name="remarks"></a>Observaciones  

 El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar. Para obtener más información acerca de los archivos XML, vea [esquema del archivo de configuración](../../configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorBindToCurrentRuntime (Función)](corbindtocurrentruntime-function.md)
- [CorBindToRuntime (Función)](corbindtoruntime-function.md)
- [CorBindToRuntimeEx (Función)](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost (Función)](corbindtoruntimehost-function.md)
- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
