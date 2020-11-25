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
ms.openlocfilehash: a8326f95286ef05dd370797a531417f81ed5c65b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723160"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="70c14-102">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="70c14-102">_CorImageUnloading Function</span></span>

<span data-ttu-id="70c14-103">Notifica al cargador cuando se descargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="70c14-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="70c14-104">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="70c14-104">This function is not implemented.</span></span> <span data-ttu-id="70c14-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="70c14-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70c14-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70c14-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70c14-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70c14-107">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="70c14-108">de Puntero a la ubicación inicial de la imagen que se va a descargar.</span><span class="sxs-lookup"><span data-stu-id="70c14-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70c14-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70c14-109">Requirements</span></span>  

 <span data-ttu-id="70c14-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70c14-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70c14-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="70c14-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70c14-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70c14-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70c14-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70c14-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c14-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70c14-114">See also</span></span>

- [<span data-ttu-id="70c14-115">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="70c14-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
