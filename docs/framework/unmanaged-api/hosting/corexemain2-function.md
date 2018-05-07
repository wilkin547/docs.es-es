---
title: _CorExeMain2 (Función)
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 573336b32040f44ff1b59fcbb75b59aa00976b5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="corexemain2-function"></a>_CorExeMain2 (Función)
Ejecuta el punto de entrada en el código asignado a la memoria especificado. Esta función se invoca por el cargador del sistema operativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pUnmappedPE`  
 [in] Un puntero al código asignado a la memoria.  
  
 `cUnmappedPE`  
 [in] El número de elementos `pUnmappedPE` puede contener.  
  
 `pImageNameIn`  
 [in] Un puntero al nombre de la imagen ejecutable.  
  
 `pLoadersFileName`  
 [in] El nombre del archivo del cargador.  
  
 `pCmdLine`  
 [in] Parámetros de línea de comandos, si hay alguno.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
