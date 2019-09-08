---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796303"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="d5ecf-102">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="d5ecf-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="d5ecf-103">Elimina la memoria caché de descarga del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d5ecf-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ecf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5ecf-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d5ecf-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5ecf-105">Return Value</span></span>  
 <span data-ttu-id="d5ecf-106">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h.</span><span class="sxs-lookup"><span data-stu-id="d5ecf-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5ecf-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5ecf-107">Remarks</span></span>  
 <span data-ttu-id="d5ecf-108">La caché de descarga de CLR es el área donde se almacenan los ensamblados con nombre seguro que se descargan de una dirección URL para poder reutilizarlos.</span><span class="sxs-lookup"><span data-stu-id="d5ecf-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ecf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5ecf-109">Requirements</span></span>  
 <span data-ttu-id="d5ecf-110">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5ecf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ecf-111">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d5ecf-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d5ecf-112">**Biblioteca** Fusion. dll y mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="d5ecf-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d5ecf-113">Use Fusion. dll en lugar de mscorwks. dll para asegurarse de que tiene como destino la versión correcta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5ecf-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d5ecf-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5ecf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ecf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5ecf-115">See also</span></span>

- [<span data-ttu-id="d5ecf-116">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="d5ecf-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="d5ecf-117">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="d5ecf-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="d5ecf-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="d5ecf-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
