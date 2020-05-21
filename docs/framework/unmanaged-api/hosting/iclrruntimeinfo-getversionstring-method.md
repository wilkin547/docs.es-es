---
title: ICLRRuntimeInfo::GetVersionString (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: ccf48b6aea25bd602b55727c2e5958811702f6bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762583"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>ICLRRuntimeInfo::GetVersionString (Método)
Obtiene la información de versión de Common Language Runtime (CLR) asociada a una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) especificada.  
  
 Este método sustituye a las siguientes funciones:  
  
- [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)  
  
- [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzBuffer`  
 enuncia La versión de compilación de .NET Framework con el formato "v*A*. *B*[.* X*] ". *A*, *B*y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación. *X* es opcional. Si *X* no está presente, no hay ningún punto final.  
  
> [!NOTE]
> Este parámetro debe coincidir con el nombre de directorio de la versión de .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework.  
  
 Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *x*", donde *x* depende del número de compilación instalado. Tenga en cuenta que el prefijo "v" es obligatorio.  
  
 `pchBuffer`  
 [in, out] Especifica el tamaño de `pwzBuffer` para evitar las saturaciones del búfer. Si `pwzBuffer` es `null` , `pchBuffer` devuelve el tamaño necesario de `pwzBuffer` para permitir la asignación previa.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pwzBuffer` o `pchBuffer` es null.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hospedar aplicaciones de WPF](index.md)
