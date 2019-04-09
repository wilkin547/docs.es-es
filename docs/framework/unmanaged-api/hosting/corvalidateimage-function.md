---
title: _CorValidateImage (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df9cc0cc86237b1ec439a4ec4fa6a75429c416d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111181"
---
# <a name="corvalidateimage-function"></a>_CorValidateImage (Función)
Valida las imágenes de módulo administrado y notifica al cargador del sistema operativo después de que se han cargado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ImageBase`  
 [in] Un puntero a la ubicación inicial de la imagen para validar como código administrado. La imagen ya se debe cargar en la memoria.  
  
 `FileName`  
 [in] El nombre de archivo de la imagen.  
  
## <a name="return-value"></a>Valor devuelto  
 Esta función devuelve los valores estándar `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, y `E_FAIL`, así como los valores siguientes.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|La imagen no es válida. Este valor tiene el resultado HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|La imagen es válida. Este valor tiene el resultado HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Comentarios  
 En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba los módulos administrados examinando el bit de directorio de Descriptor de COM en el encabezado de common object file format (COFF). Un bit establecido indica un módulo administrado. Si el cargador detecta un módulo administrado, carga MsCorEE.dll y llamadas `_CorValidateImage`, que realiza las acciones siguientes:  
  
-   Confirma que la imagen es un módulo administrado válido.  
  
-   Cambia el punto de entrada en la imagen a un punto de entrada en common language runtime (CLR).  
  
-   Para las versiones de 64 bits de Windows, modifica la imagen que está en la memoria transformando PE32 en PE32 + formato.  
  
-   Devuelve al cargador cuándo se cargan las imágenes de módulo administrado.  
  
 Para las imágenes ejecutables, el cargador del sistema operativo, a continuación, llama a la [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) función, independientemente del punto de entrada especificado en el archivo ejecutable. Para las imágenes de ensamblado DLL, el cargador llama a la [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) función.  
  
 `_CorExeMain` o `_CorDllMain` realiza las acciones siguientes:  
  
-   Inicializa el CLR.  
  
-   Busca el punto de entrada administrado desde el encabezado CLR del ensamblado.  
  
-   Empieza a ejecutarse.  
  
 Las llamadas de cargador la [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funcionando cuando administra las imágenes de módulo se descargan. Sin embargo, esta función no realiza ninguna acción; simplemente devuelve.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
