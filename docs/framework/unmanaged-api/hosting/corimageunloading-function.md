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
ms.openlocfilehash: b488b6a887b0c66d8c17f8ea78f48f7d2ea31011
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758397"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="424c2-102">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="424c2-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="424c2-103">Notifica al cargador cuándo se descargan las imágenes de módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="424c2-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="424c2-104">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="424c2-104">This function is not implemented.</span></span> <span data-ttu-id="424c2-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="424c2-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="424c2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="424c2-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="424c2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="424c2-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="424c2-108">[in] Un puntero a la ubicación inicial de la imagen para descargar.</span><span class="sxs-lookup"><span data-stu-id="424c2-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="424c2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="424c2-109">Requirements</span></span>  
 <span data-ttu-id="424c2-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="424c2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="424c2-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="424c2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="424c2-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="424c2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="424c2-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="424c2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="424c2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="424c2-114">See also</span></span>

- [<span data-ttu-id="424c2-115">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="424c2-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
