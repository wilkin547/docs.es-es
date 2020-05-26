---
title: IHostAssemblyManager::GetNonHostStoreAssemblies (Método)
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
ms.openlocfilehash: 0dc2f625da7f4e37583f198c8d6dba86f6dcdb10
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805066"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>IHostAssemblyManager::GetNonHostStoreAssemblies (Método)
Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que cargue el Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppReferenceList`  
 enuncia Puntero a la dirección de un `ICLRAssemblyReferenceList` que contiene una lista de referencias a los ensamblados que el host espera que el CLR cargue.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear la lista de referencias para el solicitado `ICLRAssemblyReferenceList` .|  
  
## <a name="remarks"></a>Observaciones  
 CLR resuelve las referencias utilizando el siguiente conjunto de instrucciones:  
  
- En primer lugar, consulta la lista de referencias de ensamblado devueltas por `GetNonHostStoreAssemblies` .  
  
- Si el ensamblado aparece en la lista, CLR se enlaza a él normalmente.  
  
- Si el ensamblado no aparece en la lista y el host ha proporcionado una implementación de [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR llama a [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) para permitir que el host proporcione el ensamblado con el que se va a enlazar.  
  
- De lo contrario, CLR no puede enlazar con el ensamblado.  
  
 Si el host establece `ppReferenceList` en null, CLR sondea primero la caché global de ensamblados, llama a `ProvideAssembly` y, a continuación, sondea la base de la aplicación para resolver una referencia de ensamblado.  
  
> [!NOTE]
> Tras la inicialización, CLR llama `GetNonHostStoreAssemblies` solo una vez. No se llama de nuevo al método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager (Interfaz)](ihostassemblymanager-interface.md)
- [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)
