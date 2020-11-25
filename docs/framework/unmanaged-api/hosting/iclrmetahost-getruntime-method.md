---
title: ICLRMetaHost::GetRuntime (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
ms.openlocfilehash: 093fa64a7d51e0c2fdc304d2bb4f1c9f7b03e2ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730414"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime (Método)

Obtiene la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que corresponde a una versión determinada del Common Language Runtime (CLR). Este método reemplaza a la función [CorBindToRuntimeEx](corbindtoruntimeex-function.md) utilizada con la marca [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pwzVersion`  
 de La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v *A*. *B*[.*X*] ". *A*, *B* y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.  
  
> [!NOTE]
> Este parámetro debe coincidir con el nombre de directorio de la versión .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.  
  
 Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *X*", donde *X* depende del número de compilación instalado. El prefijo "v" es obligatorio.  
  
 `riid`  
 de Identificador de la interfaz deseada. Actualmente, el único valor válido para este parámetro es IID_ICLRRuntimeInfo.  
  
 `ppRuntime`  
 enuncia Puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que corresponde al Runtime solicitado.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pwzVersion` o `ppRuntime` es null.|  
  
## <a name="remarks"></a>Comentarios  

 Este método interactúa de forma coherente con las interfaces heredadas como la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) y las funciones heredadas como las funciones desusadas `CorBindTo*` (vea [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2,0). Es decir, los tiempos de ejecución que se cargan con la API heredada están visibles para la nueva API y los tiempos de ejecución que se cargan con la nueva API son visibles para la API heredada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRMetaHost (Interfaz)](iclrmetahost-interface.md)
- [Coclases e interfaces de hospedaje de CLR en desuso](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [Interfaces de hospedaje de CLR](clr-hosting-interfaces.md)
- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
- [Hospedar aplicaciones de WPF](index.md)
