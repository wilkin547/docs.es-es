---
title: "_CorValidateImage (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03deb62a84a1e9c6cee898fe0023c34b8c538ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidateimage-function"></a>_CorValidateImage (Función)
Valida las imágenes del módulo administrado y notifica el cargador del sistema operativo después de que se han cargado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ImageBase`  
 [in] Un puntero a la ubicación inicial de la imagen para validar como código administrado. La imagen debe ser cargada en la memoria.  
  
 `FileName`  
 [in] El nombre de archivo de la imagen.  
  
## <a name="return-value"></a>Valor devuelto  
 Esta función devuelve los valores estándar `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, y `E_FAIL`, así como los valores siguientes.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|La imagen no es válida. Este valor tiene el resultado HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|La imagen es válida. Este valor tiene el resultado HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Comentarios  
 En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba los módulos administrados examinando el bit de directorio de Descriptor de COM en el encabezado de common object file format (COFF). Un bit establecido indica un módulo administrado. Si el cargador detecta un módulo administrado, carga MsCorEE.dll y llamadas `_CorValidateImage`, que realiza las siguientes acciones:  
  
-   Confirma que la imagen es un módulo administrado válido.  
  
-   Cambia el punto de entrada en la imagen a un punto de entrada en common language runtime (CLR).  
  
-   En las versiones de 64 bits de Windows, modifica la imagen que está en la memoria transformando PE32 en PE32 + formato.  
  
-   Devuelve al cargador cuándo se cargan las imágenes del módulo administrado.  
  
 Para las imágenes ejecutables, el cargador del sistema operativo, a continuación, llama a la [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) función, sin tener en cuenta el punto de entrada especificado en el archivo ejecutable. Para las imágenes de ensamblado del archivo DLL, el cargador llama a la [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) función.  
  
 `_CorExeMain`o `_CorDllMain` realiza las siguientes acciones:  
  
-   Inicializa el CLR.  
  
-   Busca el punto de entrada administrado en el encabezado del ensamblado CLR.  
  
-   Empieza a ejecutarse.  
  
 Las llamadas de cargador el [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funcionar cuando administrados se descargan imágenes del módulo. Sin embargo, esta función no realiza ninguna acción; simplemente devuelve.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
