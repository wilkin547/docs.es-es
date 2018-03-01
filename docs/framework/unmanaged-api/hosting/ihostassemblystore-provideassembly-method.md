---
title: "IHostAssemblyStore::ProvideAssembly (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2097c1ea64e5e9a2a09e0ec57243624b05eeea65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly (Método)
Obtiene una referencia a un ensamblado que no hace referencia la [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que se devuelve de [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Common language runtime (CLR) llama `ProvideAssembly` para cada ensamblado que no aparece en la lista.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pBindInfo`  
 [in] Un puntero a un [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instancia que usa el host para determinar ciertas características del enlace, incluida la presencia o ausencia de directivas de control de versiones así como para enlazar con el ensamblado.  
  
 `pAssemblyId`  
 [out] Un puntero a un identificador único para el ensamblado solicitado para esta `IStream`.  
  
 `pHostContext`  
 [out] Llamada de invocación de un puntero a datos específicos del host que se utilizan para determinar la evidencia del ensamblado solicitado sin necesidad de una plataforma. `pHostContext`corresponde a la <xref:System.Reflection.Assembly.HostContext%2A> propiedad de los recursos administrados <xref:System.Reflection.Assembly> clase.  
  
 `ppStmAssemblyImage`  
 [out] Un puntero a la dirección de un `IStream` que contiene la imagen ejecutable portable (PE) para cargar, o null si no se pudo encontrar el ensamblado.  
  
 `ppStmPDB`  
 [out] Un puntero a la dirección de un `IStream` que contiene la información de depuración (PDB) del programa, o null si no se encontró el archivo PDB.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0 X 80070002)|No se pudo encontrar el ensamblado solicitado.|  
|E_NOT_SUFFICIENT_BUFFER|El tamaño de búfer especificado por `pAssemblyId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.|  
  
## <a name="remarks"></a>Comentarios  
 Devuelve el valor de identidad para `pAssemblyId` especificado por el host. Identificadores deben ser únicos dentro de la duración de un proceso. CLR utiliza este valor como un identificador único para la secuencia. Comprueba cada valor con los valores para `pAssemblyId` devueltos por otras llamadas a `ProvideAssembly`. Si el host devuelve el mismo `pAssemblyId` valor por otro `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia. Si es así, el tiempo de ejecución carga la copia existente de la imagen en lugar de asignar una nueva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
