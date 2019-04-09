---
title: _CorImageUnloading (Función)
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb5f9decbcdfb71f67a5132dc59773f1de8b0a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086434"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="f2b91-102">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="f2b91-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="f2b91-103">Notifica al cargador cuándo se descargan las imágenes de módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="f2b91-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="f2b91-104">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="f2b91-104">This function is not implemented.</span></span> <span data-ttu-id="f2b91-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f2b91-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b91-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2b91-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2b91-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2b91-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="f2b91-108">[in] Un puntero a la ubicación inicial de la imagen para descargar.</span><span class="sxs-lookup"><span data-stu-id="f2b91-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2b91-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2b91-109">Requirements</span></span>  
 <span data-ttu-id="f2b91-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2b91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2b91-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2b91-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2b91-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2b91-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f2b91-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f2b91-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2b91-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2b91-114">See also</span></span>

- [<span data-ttu-id="f2b91-115">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="f2b91-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
