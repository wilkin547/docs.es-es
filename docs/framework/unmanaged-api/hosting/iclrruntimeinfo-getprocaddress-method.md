---
description: 'Más información acerca de: ICLRRuntimeInfo:: GetProcAddress (método)'
title: ICLRRuntimeInfo::GetProcAddress (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 1e5d08ed118930418106b28541b4081d6acad927
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637149"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a>ICLRRuntimeInfo::GetProcAddress (Método)

Obtiene la dirección de una función especificada que se exportó desde el Common Language Runtime (CLR) asociado a esta interfaz.  
  
 Este método reemplaza a la función [GetRealProcAddress (](getrealprocaddress-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pszProcName`  
 de Nombre de la función exportada.  
  
 `ppProc`  
 enuncia Dirección de la función exportada.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pszProcName` o `ppProc` es null.|  
|CLR_E_SHIM_RUNTIMEEXPORT|La función especificada no es una función exportada.|  
  
## <a name="remarks"></a>Observaciones  

 Este método hace que el CLR se cargue pero no se inicialice.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
