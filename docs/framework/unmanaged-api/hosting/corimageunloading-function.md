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
ms.openlocfilehash: be2edd5b217466a58aa9c478dadc10004ebda721
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556147"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="56889-102">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="56889-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="56889-103">Notifica al cargador cuándo se descargan las imágenes de módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="56889-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="56889-104">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="56889-104">This function is not implemented.</span></span> <span data-ttu-id="56889-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="56889-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56889-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56889-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56889-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56889-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="56889-108">[in] Un puntero a la ubicación inicial de la imagen para descargar.</span><span class="sxs-lookup"><span data-stu-id="56889-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56889-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56889-109">Requirements</span></span>  
 <span data-ttu-id="56889-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56889-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56889-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="56889-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56889-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56889-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="56889-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56889-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56889-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="56889-114">See also</span></span>
- [<span data-ttu-id="56889-115">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="56889-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
