---
title: IHostAssemblyManager::GetAssemblyStore (Método)
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
ms.openlocfilehash: 91c9a92d83312efcfd90a15aa0a60cccb6b44d7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134737"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a>IHostAssemblyManager::GetAssemblyStore (Método)
Obtiene un puntero de interfaz a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppAssemblyStore`  
 enuncia Un puntero de función a una instancia de `IHostAssemblyStore`, o null, si el host no implementa `IHostAssemblyStore`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetAssemblyStore` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_NOINTERFACE|El host no proporciona una implementación de `IHostAssemblyStore`.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostAssemblyStore` proporciona métodos que permiten a un host enlazarse a ensamblados y módulos independientemente de CLR. Normalmente, los hosts proporcionan almacenes de ensamblados para permitir que los ensamblados se carguen desde formatos distintos del sistema de archivos.  
  
> [!NOTE]
> Si el host no implementa `IHostAssemblyStore`, `GetAssemblyStore` debe devolver un valor HRESULT de E_NOINTERFACE y debe establecer `ppAssemblyStore` en NULL.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
