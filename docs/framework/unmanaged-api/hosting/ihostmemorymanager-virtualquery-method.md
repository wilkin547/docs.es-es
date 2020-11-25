---
title: IHostMemoryManager::VirtualQuery (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
ms.openlocfilehash: 6e3cb5bcec831f143d45f733c9e2f977390aade6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731252"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery (Método)

Actúa como un contenedor lógico para la función de Win32 correspondiente. La implementación de Win32 de `VirtualQuery` recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `lpAddress`  
 de Puntero a la dirección de la memoria virtual que se va a consultar.  
  
 `lpBuffer`  
 enuncia Puntero a una estructura que contiene información sobre la región de memoria especificada.  
  
 `dwLength`  
 de Tamaño, en bytes, del búfer `lpBuffer` al que apunta.  
  
 `pResult`  
 enuncia Puntero al número de bytes devuelto por el búfer de información.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  

 `VirtualQuery` proporciona información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada. Esta implementación establece el valor del `pResult` parámetro en el número de bytes devuelto en el búfer de información y devuelve un valor HRESULT. En la función de Win32 `VirtualQuery` , el valor devuelto es el tamaño del búfer. Para obtener más información, vea la documentación de la plataforma Windows.  
  
> [!IMPORTANT]
> La implementación del sistema operativo de no `VirtualQuery` incurre en un interbloqueo y puede ejecutarse hasta completarse con subprocesos aleatorios suspendidos en el código de usuario. Tenga mucho cuidado al implementar una versión hospedada de este método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
