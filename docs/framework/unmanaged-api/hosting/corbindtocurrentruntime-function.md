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
ms.openlocfilehash: 9c5d83b5f2ffb06c9fb14f715a3ea7ff12319086
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547836"
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime (Función)
Carga el Common Language Runtime (CLR) en un proceso utilizando la información de versión almacenada en un archivo XML. El formato del archivo XML se modela después del archivo de configuración de la aplicación estándar. Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../configure-apps/file-schema/index.md) (Esquema de archivos de configuración).  
  
 Esta función está en desuso en el .NET Framework 4. Vea [cargar Common Language Runtime en un proceso](/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).  
  
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
  
 La versión del Runtime que se va a cargar se describe mediante el atributo version en el [\<requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) elemento del archivo de configuración.  
  
 Si no se especifica ninguna versión o si `<requiredRuntime>` no se encuentra el elemento, se carga la versión más reciente de CLR que está instalada en la máquina.  
  
 `rclsid`  
 de `CLSID` De la coclase que implementa la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) o [ICLRRuntimeHost](iclrruntimehost-interface.md) . Los valores admitidos son CLSID_CorRuntimeHost o CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] El `IID` de la interfaz solicitada. Los valores admitidos son IID_ICorRuntimeHost o IID_ICLRRuntimeHost.  
  
 `ppv`  
 enuncia Puntero de interfaz devuelto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CorBindToRuntime (Función)](corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg (Función)](corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx (Función)](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost (Función)](corbindtoruntimehost-function.md)
- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
