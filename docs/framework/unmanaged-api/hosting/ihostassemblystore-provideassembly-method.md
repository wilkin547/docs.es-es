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
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124486"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly (Método)
Obtiene una referencia a un ensamblado al que no hace referencia el [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que se devuelve desde [IHostAssemblyManager:: GetNonHostStoreAssemblies (](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md). El Common Language Runtime (CLR) llama a `ProvideAssembly` para cada ensamblado que no aparece en la lista.  
  
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
 de Puntero a una instancia de [assemblybindinfo (](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) que el host usa para determinar ciertas características de enlace, incluida la presencia o ausencia de cualquier directiva de control de versiones y el ensamblado al que se va a enlazar.  
  
 `pAssemblyId`  
 enuncia Un puntero a un identificador único para el ensamblado solicitado para esta `IStream`.  
  
 `pHostContext`  
 enuncia Puntero a los datos específicos del host que se usan para determinar la evidencia del ensamblado solicitado sin necesidad de una llamada de invocación de plataforma. `pHostContext` corresponde a la propiedad <xref:System.Reflection.Assembly.HostContext%2A> de la clase <xref:System.Reflection.Assembly> administrada.  
  
 `ppStmAssemblyImage`  
 enuncia Puntero a la dirección de una `IStream` que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se pudo encontrar el ensamblado.  
  
 `ppStmPDB`  
 enuncia Puntero a la dirección de una `IStream` que contiene la información de depuración del programa (PDB) o null si no se encuentra el archivo. pdb.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|COR_E_FILENOTFOUND (0x80070002)|No se pudo encontrar el ensamblado solicitado.|  
|E_NOT_SUFFICIENT_BUFFER|El tamaño de búfer especificado por `pAssemblyId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.|  
  
## <a name="remarks"></a>Comentarios  
 El host especifica el valor de identidad devuelto para `pAssemblyId`. Los identificadores deben ser únicos dentro de la duración de un proceso. CLR usa este valor como un identificador único para la secuencia. Comprueba cada valor con los valores de `pAssemblyId` devueltos por otras llamadas a `ProvideAssembly`. Si el host devuelve el mismo valor `pAssemblyId` para otro `IStream`, CLR comprueba si ya se ha asignado el contenido de la secuencia. En ese caso, el tiempo de ejecución carga la copia existente de la imagen en lugar de asignar una nueva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
