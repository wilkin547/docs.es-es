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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178215"
---
# <a name="_corvalidateimage-function"></a>_CorValidateImage (Función)
Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez cargadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ImageBase`  
 [en] Puntero a la ubicación inicial de la imagen para validarla como código administrado. La imagen ya debe estar cargada en la memoria.  
  
 `FileName`  
 [en] El nombre de archivo de la imagen.  
  
## <a name="return-value"></a>Valor devuelto  
 Esta función devuelve `E_INVALIDARG` `E_OUTOFMEMORY`los `E_UNEXPECTED`valores `E_FAIL`estándar , , , y , así como los siguientes valores.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|La imagen no es válida. Este valor tiene el HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|La imagen es válida. Este valor tiene el HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Observaciones  
 En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba si hay módulos administrados examinando el bit del directorio del descriptor COM en el encabezado de formato de archivo de objeto común (COFF). Un bit de conjunto indica un módulo administrado. Si el cargador detecta un módulo administrado, carga MsCorEE.dll y llama, `_CorValidateImage`que realiza las siguientes acciones:  
  
- Confirma que la imagen es un módulo administrado válido.  
  
- Cambia el punto de entrada de la imagen a un punto de entrada en Common Language Runtime (CLR).  
  
- Para las versiones de 64 bits de Windows, modifica la imagen que está en memoria transformándola de formato PE32 a PE32+.  
  
- Vuelve al cargador cuando se cargan las imágenes del módulo administrado.  
  
 Para las imágenes ejecutables, el cargador del sistema operativo llama a la función [_CorExeMain,](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) independientemente del punto de entrada especificado en el ejecutable. Para las imágenes de ensamblado DLL, el cargador llama a la función [_CorDllMain.](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
  
 `_CorExeMain`o `_CorDllMain` realiza las siguientes acciones:  
  
- Inicializa el CLR.  
  
- Busca el punto de entrada administrado desde el encabezado CLR del ensamblado.  
  
- Comienza la ejecución.  
  
 El cargador llama a la función [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) cuando se descargan imágenes de módulo sadministradas. Sin embargo, esta función no realiza ninguna acción; simplemente regresa.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
