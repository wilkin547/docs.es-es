---
description: 'Más información acerca de: ICLRRuntimeInfo:: Getdefaultstartupflags ((método)'
title: ICLRRuntimeInfo::GetDefaultStartupFlags (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: c6afb19319fd24d499c2c216f2ce0adc2e7a886c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637185"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags (Método)

Obtiene las marcas de inicio y el archivo de configuración de host que se usarán para iniciar el tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pdwStartupFlags`  
 enuncia Puntero a las marcas de inicio del host que están establecidas actualmente.  
  
 `pwzHostConfigFile`  
 enuncia Puntero a la ruta de acceso al directorio del archivo de configuración del host actual.  
  
 `pcchHostConfigFile`  
 [in, out] En la entrada, el tamaño de `pwzHostConfigFile` , para evitar las saturaciones del búfer. Si `pwzHostConfigFile` es null, el método devuelve el tamaño necesario de `pwzHostConfigFile` para la asignación previa.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
  
## <a name="remarks"></a>Observaciones  

 Este método devuelve los valores de marca predeterminados ( `STARTUP_CONCURRENT_GC` y `NULL` ), o los valores proporcionados por una llamada anterior al [método ICLRRuntimeInfo:: SetDefaultStartupFlags (](iclrruntimeinfo-setdefaultstartupflags-method.md), o los valores establecidos por cualquiera de los `CorBind*` métodos si están enlazados a este Runtime.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
