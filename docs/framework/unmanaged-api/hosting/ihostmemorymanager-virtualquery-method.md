---
title: "IHostMemoryManager::VirtualQuery (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualQuery
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82c76ce908dd73fba0a2a0039894f51790b46583
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery (Método)
Actúa como un contenedor lógico para la función de Win32 correspondiente. La implementación de Win32 de `VirtualQuery` recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `lpAddress`  
 [in] Un puntero a la dirección en la memoria virtual y pueden consultar.  
  
 `lpBuffer`  
 [out] Un puntero a una estructura que contiene información acerca de la región de memoria especificada.  
  
 `dwLength`  
 [in] El tamaño, en bytes, del búfer que `lpBuffer` apunta a.  
  
 `pResult`  
 [out] Un puntero al número de bytes devueltos en el búfer de información.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`VirtualQuery`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 `VirtualQuery`Proporciona información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada. Esta implementación establece el valor de la `pResult` parámetro para el número de bytes devueltos en el búfer de información y devuelve un valor HRESULT. En Win32 `VirtualQuery` función, el valor devuelto es el tamaño del búfer. Para obtener más información, consulte la documentación de la plataforma de Windows.  
  
> [!IMPORTANT]
>  Implementación del sistema operativo de `VirtualQuery` no incurre en interbloqueos y puede ejecutarse hasta su finalización con subprocesos aleatorios suspendidos en el código de usuario. Usar mucha precaución al implementar una versión hospedada de este método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
