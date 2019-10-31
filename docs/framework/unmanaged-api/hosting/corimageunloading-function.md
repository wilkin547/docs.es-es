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
ms.openlocfilehash: 30e3a88140c8a438001e8428df4c5ee879c83376
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136922"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="fbe0b-102">_CorImageUnloading (Función)</span><span class="sxs-lookup"><span data-stu-id="fbe0b-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="fbe0b-103">Notifica al cargador cuando se descargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="fbe0b-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="fbe0b-104">Esta función no está implementada.</span><span class="sxs-lookup"><span data-stu-id="fbe0b-104">This function is not implemented.</span></span> <span data-ttu-id="fbe0b-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="fbe0b-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbe0b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbe0b-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbe0b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fbe0b-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="fbe0b-108">de Puntero a la ubicación inicial de la imagen que se va a descargar.</span><span class="sxs-lookup"><span data-stu-id="fbe0b-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbe0b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbe0b-109">Requirements</span></span>  
 <span data-ttu-id="fbe0b-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbe0b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbe0b-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fbe0b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fbe0b-112">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fbe0b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fbe0b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbe0b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe0b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbe0b-114">See also</span></span>

- [<span data-ttu-id="fbe0b-115">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="fbe0b-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
