---
description: 'Más información acerca de: ICLRMetaHost:: EnumerateLoadedRuntimes (método)'
title: ICLRMetaHost::EnumerateLoadedRuntimes (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: 508c4daca7e34366e0da35591f4e7a780301e823
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789871"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a>ICLRMetaHost::EnumerateLoadedRuntimes (Método)

Devuelve una enumeración que incluye un puntero de interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válido para cada versión del Common Language Runtime (CLR) que se carga en un proceso determinado. Este método reemplaza a la función [GetVersionFromProcess (](getversionfromprocess-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `hndProcess`  
 de Identificador del proceso para inspeccionar los tiempos de ejecución cargados.  
  
 `ppEnumerator`  
 enuncia Una <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeración de las interfaces [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) correspondientes a cada CLR que carga el proceso.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`ppEnumerator` es null.|  
  
## <a name="remarks"></a>Observaciones  

 Este método muestra todos los tiempos de ejecución cargados, incluso si se cargaron con funciones desusadas como [CorBindToRuntime](corbindtoruntime-function.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRMetaHost (Interfaz)](iclrmetahost-interface.md)
- [Hospedar aplicaciones de WPF](index.md)
