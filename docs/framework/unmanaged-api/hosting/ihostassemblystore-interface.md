---
title: IHostAssemblyStore (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173425"
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore (Interfaz)
Proporciona métodos que permiten a un host cargar ensamblados y módulos con independencia de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Obtiene una referencia a un ensamblado que no hace referencia el [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) devueltos por una llamada a [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[Método ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Resuelve un módulo dentro de un ensamblado o un archivo de recursos (no incrustado) vinculados.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostAssemblyStore` Proporciona una manera para un host cargar ensamblados eficazmente basándose en la identidad del ensamblado. El host carga ensamblados devolviendo `IStream` instancias que apuntan directamente a los bytes.  
  
 El CLR para determinar si se ha implementado un host `IHostAssemblyStore` mediante una llamada a `IHostAssemblyManager::GetNonHostAssemblyStores` tras la inicialización. Esto permite al host, por ejemplo, para controlar el enlace a los ensamblados de usuario, sino que se basarán en el tiempo de ejecución para enlazar a ensamblados de .NET Framework.  
  
> [!NOTE]
>  Al proporcionar una implementación de `IHostAssemblyStore`, el host especifica su intento de resolver todos los ensamblados que no hace referencia el `ICLRAssemblyReferenceList` devuelto desde `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
>  La versión 2.0 de .NET Framework no proporciona una forma para el host cargar la imagen nativa de un ensamblado, tal como lo proporciona el [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilidad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
