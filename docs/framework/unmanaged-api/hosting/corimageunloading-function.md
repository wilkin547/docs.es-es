---
title: "_CorImageUnloading (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorImageUnloading
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorImageUnloading
helpviewer_keywords: _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90df58e2765cdecf4a1ec22cf5540e5cfa9530a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="c36eb-102">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="c36eb-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="c36eb-103">Notifica al cargador cuándo se descargan imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="c36eb-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="c36eb-104">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="c36eb-104">This function is not implemented.</span></span> <span data-ttu-id="c36eb-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c36eb-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36eb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c36eb-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c36eb-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c36eb-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="c36eb-108">[in] Un puntero a la ubicación inicial de la imagen a punto de descargarse.</span><span class="sxs-lookup"><span data-stu-id="c36eb-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c36eb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c36eb-109">Requirements</span></span>  
 <span data-ttu-id="c36eb-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c36eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c36eb-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c36eb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c36eb-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c36eb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c36eb-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c36eb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36eb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c36eb-114">See Also</span></span>  
 [<span data-ttu-id="c36eb-115">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="c36eb-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
