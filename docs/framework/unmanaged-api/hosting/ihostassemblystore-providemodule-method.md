---
description: 'Más información acerca de: IHostAssemblyStore::P método rovideModule'
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
ms.openlocfilehash: 9e783b9f8db303d095995507689d7567225a51fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709033"
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
 de Puntero a una instancia de [modulebindinfo (](modulebindinfo-structure.md) que describe el <xref:System.AppDomain> ensamblado, el ensamblado y el nombre del módulo solicitados.  
  
 `pdwModuleId`  
 enuncia Un puntero a un identificador único para `IStream` que contiene el módulo cargado.  
  
 `ppStmModuleImage`  
 enuncia Un puntero a la dirección de un `IStream` objeto, que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se encuentra el módulo.  
  
 `ppStmPDB`  
 enuncia Puntero a la dirección de un `IStream` objeto, que contiene la información de depuración del programa (PDB) para el módulo solicitado, o null si no se encuentra el archivo. pdb.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ProvideModule` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|No se encontró el ensamblado o el recurso vinculado solicitado.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.|  
  
## <a name="remarks"></a>Observaciones  

 El valor de identidad devuelto por `pdwModuleId` se especifica mediante el host. Los identificadores deben ser únicos dentro de la duración de un proceso. CLR usa este valor como identificador único para la secuencia asociada. Comprueba cada valor con los valores `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](ihostassemblystore-provideassembly-method.md) y con los valores `pdwModuleId` devueltos por otras llamadas a `ProvideModule` . Si el host devuelve el mismo valor de identificador para otro `IStream` , CLR comprueba si ya se ha asignado el contenido de la secuencia. Si es así, CLR carga la copia existente de la imagen en lugar de asignar una nueva. Por lo tanto, el identificador tampoco debe superponerse con los identificadores de ensamblado devueltos por `ProvideAssembly` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (Interfaz)](ihostassemblymanager-interface.md)
- [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)
