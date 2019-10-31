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
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124471"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule (Método)
Resuelve un módulo dentro de un ensamblado o un archivo de recursos vinculado (pero no incrustado).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pBindInfo`  
 de Un puntero a una instancia de [modulebindinfo (](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) que describe el <xref:System.AppDomain>, el ensamblado y el nombre del módulo solicitados.  
  
 `pdwModuleId`  
 enuncia Un puntero a un identificador único para el `IStream` que contiene el módulo cargado.  
  
 `ppStmModuleImage`  
 enuncia Puntero a la dirección de un objeto `IStream`, que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se encuentra el módulo.  
  
 `ppStmPDB`  
 enuncia Puntero a la dirección de un objeto `IStream`, que contiene la información de depuración del programa (PDB) para el módulo solicitado, o null si no se encuentra el archivo. pdb.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ProvideModule` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|No se encontró el ensamblado o el recurso vinculado solicitado.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.|  
  
## <a name="remarks"></a>Comentarios  
 El host especifica el valor de identidad devuelto para `pdwModuleId`. Los identificadores deben ser únicos dentro de la duración de un proceso. CLR usa este valor como identificador único para la secuencia asociada. Comprueba cada valor con los valores de `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) y con los valores de `pdwModuleId` devueltos por otras llamadas a `ProvideModule`. Si el host devuelve el mismo valor de identificador para otro `IStream`, CLR comprueba si ya se ha asignado el contenido de la secuencia. Si es así, CLR carga la copia existente de la imagen en lugar de asignar una nueva. Por lo tanto, el identificador tampoco debe superponerse con los identificadores de ensamblado devueltos por `ProvideAssembly`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
