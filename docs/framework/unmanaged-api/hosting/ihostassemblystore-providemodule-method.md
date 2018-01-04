---
title: "IHostAssemblyStore::ProvideModule (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b29f19933ae985d15627d1eba2622f350a52e72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule (Método)
Resuelve un módulo dentro de un ensamblado o vinculado (pero no incrustado) del archivo de recursos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pBindInfo`  
 [in] Un puntero a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instancia que describe el módulo solicitado <xref:System.AppDomain>, ensamblado y nombre del módulo.  
  
 `pdwModuleId`  
 [out] Un puntero a un identificador único para el `IStream` que contiene el módulo cargado.  
  
 `ppStmModuleImage`  
 [out] Un puntero a la dirección de un `IStream` de objeto, que contiene la imagen ejecutable portable (PE) que va a cargar, o null si no se encontró el módulo.  
  
 `ppStmPDB`  
 [out] Un puntero a la dirección de un `IStream` de objeto, que contiene la información de depuración (PDB) del programa para el módulo solicitado, o null si no se encontró el archivo PDB.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ProvideModule`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0 X 80070002)|No se encuentra el ensamblado solicitado o el recurso vinculado.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId`no es lo suficientemente grande como para contener el identificador que el host desea devolver.|  
  
## <a name="remarks"></a>Comentarios  
 Devuelve el valor de identidad para `pdwModuleId` especificado por el host. Identificadores deben ser únicos dentro de la duración de un proceso. El CLR usa este valor como identificador único para la secuencia asociada. Comprueba cada valor con los valores para `pAssemblyId` devueltos por llamadas a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) y con los valores de `pdwModuleId` devueltos por otras llamadas a `ProvideModule`. Si el host devuelve el mismo valor de identificador para otro `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia. Si es así, el CLR carga la copia existente de la imagen en lugar de asignar una nueva. Por lo tanto, el identificador también no debe solaparse con los identificadores de ensamblado devueltos por `ProvideAssembly`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
