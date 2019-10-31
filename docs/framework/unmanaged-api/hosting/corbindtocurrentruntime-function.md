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
ms.openlocfilehash: 77a0a8f58c11673a1958d837b4c3a21a05754c94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138318"
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime (Función)
Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML. El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar. Para obtener más información sobre los archivos de configuración, vea [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).  
  
 Esta función está en desuso en el .NET Framework 4. Vea [cargar Common Language Runtime en un proceso](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwszFileName`  
 de Nombre de un archivo de configuración de la aplicación que especifica la versión de CLR que se va a cargar. Si el nombre de archivo no es completo, se supone que está en el mismo directorio que el ejecutable que realiza la llamada.  
  
 La versión del tiempo de ejecución que se va a cargar se describe mediante el atributo version del elemento [\<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) del archivo de configuración.  
  
 Si no se especifica ninguna versión o si no se encuentra el elemento `<requiredRuntime>`, se carga la versión más reciente de CLR que está instalada en la máquina.  
  
 `rclsid`  
 de `CLSID` de la coclase que implementa la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) o [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) . Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] El `IID` de la interfaz solicitada. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 enuncia Puntero de interfaz devuelto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorBindToRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
