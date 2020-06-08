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
ms.openlocfilehash: 8b7dcdcc6d9d0106af1bb83ee591cff76239b416
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504461"
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
 de `CLSID`De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 de `IID`De la `ICorRuntimeHost` `ICLRRuntimeHost` interfaz o. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 enuncia Puntero a la dirección de la interfaz devuelta.  
  
## <a name="remarks"></a>Comentarios  
 El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar. Para obtener más información acerca de los archivos XML, vea [esquema del archivo de configuración](../../configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [CorBindToCurrentRuntime (Función)](corbindtocurrentruntime-function.md)
- [CorBindToRuntime (Función)](corbindtoruntime-function.md)
- [CorBindToRuntimeEx (Función)](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost (Función)](corbindtoruntimehost-function.md)
- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
