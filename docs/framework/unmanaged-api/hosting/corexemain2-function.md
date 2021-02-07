---
description: 'Más información acerca de: _CorExeMain2 función'
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
ms.openlocfilehash: 4629ea2f6c2ba13351c409bc382077eea926b507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717113"
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
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
