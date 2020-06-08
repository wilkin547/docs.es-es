---
title: ICLRRuntimeInfo::SetDefaultStartupFlags (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: aa02d42511a863434fef236f90afae2c5417a78d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504022"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>ICLRRuntimeInfo::SetDefaultStartupFlags (Método)
Establece las marcas de inicio y el archivo de configuración de host que se usarán para iniciar el tiempo de ejecución. Este método reemplaza el uso del `startupFlags` parámetro en las funciones [CorBindToRuntimeEx](corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwStartupFlags`  
 de Marcas de inicio del host que se van a establecer. Utilice las mismas marcas que con las funciones [CorBindToRuntimeEx](corbindtoruntimeex-function.md) y [CorBindToRuntimeHost](corbindtoruntimehost-function.md) .  
  
 `pwzHostConfigFile`  
 de Ruta de acceso al directorio del archivo de configuración de host que se va a establecer.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Un host multiproceso debe sincronizar las llamadas a este método. De lo contrario, el subproceso A podría llamar al método después de que el `SetStartupFlags` subproceso b complete una llamada a `SetStartupFlags` y antes de que el subproceso b inicie el tiempo de ejecución.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
