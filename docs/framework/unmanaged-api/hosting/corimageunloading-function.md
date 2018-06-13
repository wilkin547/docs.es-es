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
ms.openlocfilehash: ebd7ef3b329eae8e35b680f3d8c74864e2a0f4d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428692"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="787e1-102">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="787e1-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="787e1-103">Notifica al cargador cuándo se descargan imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="787e1-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="787e1-104">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="787e1-104">This function is not implemented.</span></span> <span data-ttu-id="787e1-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="787e1-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787e1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="787e1-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="787e1-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="787e1-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="787e1-108">[in] Un puntero a la ubicación inicial de la imagen a punto de descargarse.</span><span class="sxs-lookup"><span data-stu-id="787e1-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="787e1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="787e1-109">Requirements</span></span>  
 <span data-ttu-id="787e1-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="787e1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="787e1-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="787e1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="787e1-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="787e1-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="787e1-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="787e1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787e1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="787e1-114">See Also</span></span>  
 [<span data-ttu-id="787e1-115">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="787e1-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
