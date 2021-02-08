---
description: 'Más información acerca de: Nukedownloadedcache ((función)'
title: NukeDownloadedCache (Función)
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 2239473b8e6e43a539b0507c8255d40f87e72043
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800037"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="d0b81-103">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="d0b81-103">NukeDownloadedCache Function</span></span>

<span data-ttu-id="d0b81-104">Elimina la memoria caché de descarga del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d0b81-104">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b81-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0b81-105">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d0b81-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0b81-106">Return Value</span></span>  

 <span data-ttu-id="d0b81-107">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h.</span><span class="sxs-lookup"><span data-stu-id="d0b81-107">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0b81-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d0b81-108">Remarks</span></span>  

 <span data-ttu-id="d0b81-109">La caché de descarga de CLR es el área donde se almacenan los ensamblados con nombre seguro que se descargan de una dirección URL para poder reutilizarlos.</span><span class="sxs-lookup"><span data-stu-id="d0b81-109">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b81-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0b81-110">Requirements</span></span>  

 <span data-ttu-id="d0b81-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0b81-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b81-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d0b81-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d0b81-113">**Biblioteca:** Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="d0b81-113">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d0b81-114">Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0b81-114">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d0b81-115">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b81-115">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b81-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0b81-116">See also</span></span>

- [<span data-ttu-id="d0b81-117">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="d0b81-117">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="d0b81-118">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="d0b81-118">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="d0b81-119">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="d0b81-119">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
