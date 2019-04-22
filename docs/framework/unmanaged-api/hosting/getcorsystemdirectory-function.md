---
title: GetCORSystemDirectory (Función)
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 567e6533a9a9ac718f8b5acac769295c104f7f3c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144331"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory (Función)
Devuelve el directorio de instalación de common language runtime (CLR) que se carga en el proceso. El directorio de instalación se completa, por ejemplo, "c:\windows\microsoft.net\framework\v1.0.3705".  
  
 Esta función está en desuso. Sustituida por la [GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) método proporcionado en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Parámetros  
 `pbuffer`  
 [out] Un búfer en el que el tiempo de ejecución devuelve una cadena que contiene el nombre completo del directorio de instalación para el tiempo de ejecución que se carga en el proceso. Si el tiempo de ejecución aún no se han cargado en el proceso, la función devuelve la información de directorio adecuado para la versión más reciente del runtime instalada en el equipo.  
  
 `cchBuffer`  
 [in] El tamaño, en bytes, de `pbuffer`.  
  
 `dwLength`  
 [out] El número de caracteres devuelto en `pbuffer`.  
  
## <a name="remarks"></a>Comentarios  
  
> [!CAUTION]
>  No use esta función en procesos que se ejecutan la versión 4 de CLR. Si está instalada una versión anterior de CLR en el equipo, esta función devuelve el directorio de instalación de esa versión.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
