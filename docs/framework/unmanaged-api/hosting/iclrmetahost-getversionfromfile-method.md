---
title: ICLRMetaHost::GetVersionFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
ms.openlocfilehash: f5e0ead41ebd13c259c24fa0c02bcc9a3b33e0fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689451"
---
# <a name="iclrmetahostgetversionfromfile-method"></a>ICLRMetaHost::GetVersionFromFile (Método)

Obtiene la versión de compilación .NET Framework original de un ensamblado (almacenada en los metadatos), dada su ruta de acceso al archivo. Este método reemplaza a la función [GetFileVersion (](getfileversion-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pwzFilePath`  
 de Ruta de acceso completa del archivo de ensamblado.  
  
 `pwzbuffer`  
 enuncia La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v *A*. *B*[.*X*] ". *A*, *B* y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación. La longitud de esta cadena se limita a MAX_PATH.  
  
> [!NOTE]
> Esta salida coincide con el nombre de directorio para la versión .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework.  
  
 Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *X*", donde *X* depende del número de compilación instalado. Tenga en cuenta que el prefijo "v" es obligatorio.  
  
 `pcchBuffer`  
 [in, out] Tamaño de `pwzbuffer` para evitar las saturaciones del búfer.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pwzbuffer` o `pcchBuffer` es null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|El búfer es demasiado pequeño.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRMetaHost (Interfaz)](iclrmetahost-interface.md)
- [Hospedar aplicaciones de WPF](index.md)
