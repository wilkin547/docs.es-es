---
title: IHostAssemblyStore::ProvideModule (Método)
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078343"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule (Método)
Se resuelve como un archivo de recursos de módulo dentro de un ensamblado o vinculado (pero no incrustado).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pBindInfo`  
 [in] Un puntero a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instancia que describe el módulo solicitado <xref:System.AppDomain>, ensamblado y el nombre del módulo.  
  
 `pdwModuleId`  
 [out] Un puntero a un identificador único para el `IStream` que contiene el módulo cargado.  
  
 `ppStmModuleImage`  
 [out] Un puntero a la dirección de un `IStream` de objeto, que contiene la imagen ejecutable portable (PE) que va a cargar, o null si no se pudo encontrar el módulo.  
  
 `ppStmPDB`  
 [out] Un puntero a la dirección de un `IStream` de objeto, que contiene la información de depuración (PDB) de programa para el módulo solicitado, o null si no se encontró el archivo PDB.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ProvideModule` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0 X 80070002)|No se pudo encontrar el ensamblado solicitado o el recurso vinculado.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` no es suficientemente grande como para contener el identificador que el host desea devolver.|  
  
## <a name="remarks"></a>Comentarios  
 Devuelve el valor de identidad para `pdwModuleId` especificado por el host. Identificadores deben ser únicos dentro de la duración de un proceso. CLR usa este valor como identificador único para la secuencia asociada. Comprueba cada valor con los valores de `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) y con los valores de `pdwModuleId` devueltos por otras llamadas a `ProvideModule`. Si el host devuelve el mismo valor de identificador para otra `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia. Si es así, el CLR carga la copia existente de la imagen en lugar de asignar una nueva. Por lo tanto, el identificador también no debe solaparse con los identificadores del ensamblado devuelto desde `ProvideAssembly`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
