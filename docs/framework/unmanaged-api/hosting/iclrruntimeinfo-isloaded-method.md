---
title: ICLRRuntimeInfo::IsLoaded (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 45e27ac3c2d4912d2ed3e5d43ea3020b9db5dbdc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504035"
---
# <a name="iclrruntimeinfoisloaded-method"></a>ICLRRuntimeInfo::IsLoaded (Método)
Indica si el Common Language Runtime (CLR) asociado a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) se carga en un proceso. Un tiempo de ejecución se puede cargar sin que se inicie también.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a>Parámetros  
 `hndProcess`  
 de Identificador del proceso.  
  
 `pbLoaded`  
 [out] `true` Si el CLR se carga en el proceso; en caso contrario, `false` .  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pbLoaded` es null.|  
  
## <a name="remarks"></a>Comentarios  
 Este método es compatible con las versiones anteriores de las siguientes funciones e interfaces:  
  
- [ICorRuntimeHost](icorruntimehost-interface.md) (interfaz) (en la API de hospedaje de .NET Framework versión 1).  
  
- Interfaz [ICLRRuntimeHost](iclrruntimehost-interface.md) (en la API de hospedaje .NET Framework 2,0).  
  
- `CorBindTo*`Funciones en desuso (consulte [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2,0).  
  
 Un host puede llamar a una de las `CorBindTo*` funciones en desuso, como la función [CorBindToRuntime](corbindtoruntime-function.md) , para crear una instancia de una versión específica de CLR. Después, el host podría llamar al método [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) y especificar el mismo número de versión para obtener una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Si el host llama a continuación al `IsLoaded` método en la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) devuelta, `pbLoaded` devuelve; de `true` lo contrario, devuelve `false` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
