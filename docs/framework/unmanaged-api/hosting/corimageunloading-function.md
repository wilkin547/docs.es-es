---
description: 'Más información acerca de: _CorImageUnloading función'
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
ms.openlocfilehash: fe10c97be66aab21793b1ad306aa5d90eaa1ade2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716996"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="d245e-103">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="d245e-103">_CorImageUnloading Function</span></span>

<span data-ttu-id="d245e-104">Notifica al cargador cuando se descargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="d245e-104">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="d245e-105">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="d245e-105">This function is not implemented.</span></span> <span data-ttu-id="d245e-106">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="d245e-106">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d245e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d245e-107">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d245e-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d245e-108">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="d245e-109">de Puntero a la ubicación inicial de la imagen que se va a descargar.</span><span class="sxs-lookup"><span data-stu-id="d245e-109">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d245e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d245e-110">Requirements</span></span>  

 <span data-ttu-id="d245e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d245e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d245e-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d245e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d245e-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d245e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d245e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d245e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d245e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d245e-115">See also</span></span>

- [<span data-ttu-id="d245e-116">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="d245e-116">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
