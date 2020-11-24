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
ms.openlocfilehash: a3fb9d87b6433d46dad081619e0692a42219408d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673632"
---
# <a name="_corexemain2-function"></a>_CorExeMain2 (Función)

Ejecuta el punto de entrada en el código asignado a la memoria especificado. El cargador del sistema operativo llama a esta función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pUnmappedPE`  
 de Puntero al código asignado a la memoria.  
  
 `cUnmappedPE`  
 de Número de elementos que `pUnmappedPE` puede contener.  
  
 `pImageNameIn`  
 de Puntero al nombre de la imagen ejecutable.  
  
 `pLoadersFileName`  
 de Nombre del archivo del cargador.  
  
 `pCmdLine`  
 de Parámetros de línea de comandos, si los hay.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
