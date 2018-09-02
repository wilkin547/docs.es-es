---
title: CorBindToCurrentRuntime (Función)
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021f2b7a720c2190d56bdb2b35214c581a7b5f56
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43456940"
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime (Función)
Carga common language runtime (CLR) en un proceso mediante el uso de información de versión almacenada en un archivo XML. El formato del archivo XML se modela después del archivo de configuración de aplicación estándar. Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Consulte [cargar Common Language Runtime en un proceso](https://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwszFileName`  
 [in] El nombre de un archivo de configuración que especifica la versión de CLR para cargar. Si el nombre de archivo no es un nombre completo, se supone que para estar en el mismo directorio que el ejecutable que realiza la llamada.  
  
 Se describe la versión del runtime que se cargue por el atributo de versión en el [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) elemento del archivo de configuración.  
  
 Si se especifica ninguna versión, o si el `<requiredRuntime>` no se encuentra el elemento, se carga la última versión de CLR que está instalado en el equipo.  
  
 `rclsid`  
 [in] El `CLSID` de la coclase que implementa el [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interfaz. Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] El `IID` de la interfaz solicitada. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] El puntero de interfaz devuelto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [CorBindToRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
