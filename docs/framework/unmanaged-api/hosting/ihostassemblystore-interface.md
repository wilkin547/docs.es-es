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
ms.openlocfilehash: 5620df2ab2b2530332df02cf3f11a00d6b6c8fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore (Interfaz)
Proporciona métodos que permiten a un host cargar ensamblados y módulos con independencia de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ProvideAssembly (método)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Obtiene una referencia a un ensamblado que no hace referencia la [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) devuelto desde una llamada a [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[ProvideModule (método)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Resuelve un módulo dentro de un ensamblado o un archivo de recursos (no incrustado) vinculados.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostAssemblyStore` Proporciona una manera para que un host cargar los ensamblados eficazmente basándose en la identidad del ensamblado. El host carga los ensamblados devolviendo `IStream` instancias que apuntan directamente a los bytes.  
  
 CLR determina si un host ha implementado `IHostAssemblyStore` mediante una llamada a `IHostAssemblyManager::GetNonHostAssemblyStores` en la inicialización. Esto permite al host, por ejemplo, para controlar el enlace a los ensamblados de usuario, sino que se basarán en el tiempo de ejecución para enlazar a ensamblados de .NET Framework.  
  
> [!NOTE]
>  Para proporcionar una implementación de `IHostAssemblyStore`, el host especifica su intento de resolver todos los ensamblados que no tienen referencias en el `ICLRAssemblyReferenceList` devuelto desde `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
>  La versión 2.0 de .NET Framework no proporciona una manera para que el host cargar la imagen nativa de un ensamblado, proporcionados por el [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utilidad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
