---
title: IHostAssemblyStore::ProvideAssembly (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5fab4ef0d67ab6b86510bd4b2f814d9456213fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763994"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly (Método)
Obtiene una referencia a un ensamblado que no hace referencia el [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) devuelto desde [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). Common language runtime (CLR) llama `ProvideAssembly` para cada ensamblado que no aparece en la lista.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pBindInfo`  
 [in] Un puntero a un [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instancia que usa el host para determinar ciertas características del enlace, incluida la presencia o ausencia de directivas de control de versiones así como para enlazar con el ensamblado.  
  
 `pAssemblyId`  
 [out] Un puntero a un identificador único para el ensamblado solicitado para esta `IStream`.  
  
 `pHostContext`  
 [out] Llamada de invocación de un puntero a datos específicos del host que se usan para determinar la evidencia del ensamblado solicitado sin necesidad de una plataforma. `pHostContext` corresponde a la <xref:System.Reflection.Assembly.HostContext%2A> propiedad de los recursos administrados <xref:System.Reflection.Assembly> clase.  
  
 `ppStmAssemblyImage`  
 [out] Un puntero a la dirección de un `IStream` que contiene la imagen ejecutable portable (PE) para cargar, o null si no se encontró el ensamblado.  
  
 `ppStmPDB`  
 [out] Un puntero a la dirección de un `IStream` que contiene la información de depuración (PDB) del programa, o null si no se encontró el archivo PDB.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0 X 80070002)|No se pudo encontrar el ensamblado solicitado.|  
|E_NOT_SUFFICIENT_BUFFER|El tamaño de búfer especificado por `pAssemblyId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.|  
  
## <a name="remarks"></a>Comentarios  
 Devuelve el valor de identidad para `pAssemblyId` especificado por el host. Identificadores deben ser únicos dentro de la duración de un proceso. CLR utiliza este valor como un identificador único para la secuencia. Comprueba cada valor con los valores de `pAssemblyId` devueltos por otras llamadas a `ProvideAssembly`. Si el host devuelve el mismo `pAssemblyId` valor por otro `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia. Si es así, el tiempo de ejecución carga la copia existente de la imagen en lugar de asignar una nueva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
