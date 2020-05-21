---
title: ICLRRuntimeInfo::LoadLibrary (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 09c80c3a56d86943ebe00e5222bb5452ab44e150
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762180"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a>ICLRRuntimeInfo::LoadLibrary (Método)
Carga una biblioteca de .NET Framework desde el Common Language Runtime (CLR) representado por una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Este método reemplaza a la función [LoadLibraryShim (](loadlibraryshim-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzDllName`  
 de Nombre del ensamblado que se va a cargar.  
  
 `phndModule`  
 enuncia Identificador del ensamblado cargado.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pwzDllName` o `phndModule` es null.|  
|E_OUTOFMEMORY|No hay suficiente memoria disponible para controlar la solicitud.|  
  
## <a name="remarks"></a>Comentarios  
 Este método solo carga los archivos dll incluidos en el paquete redistribuible de .NET Framework. No puede cargar los ensamblados generados por el usuario.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
