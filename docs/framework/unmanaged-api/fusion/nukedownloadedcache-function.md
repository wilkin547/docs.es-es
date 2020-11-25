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
ms.openlocfilehash: 5ae0a887d666a150b717d495848c8a411d030a09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728581"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="33c80-102">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="33c80-102">NukeDownloadedCache Function</span></span>

<span data-ttu-id="33c80-103">Elimina la memoria caché de descarga del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="33c80-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33c80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33c80-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="33c80-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33c80-105">Return Value</span></span>  

 <span data-ttu-id="33c80-106">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h.</span><span class="sxs-lookup"><span data-stu-id="33c80-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33c80-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33c80-107">Remarks</span></span>  

 <span data-ttu-id="33c80-108">La caché de descarga de CLR es el área donde se almacenan los ensamblados con nombre seguro que se descargan de una dirección URL para poder reutilizarlos.</span><span class="sxs-lookup"><span data-stu-id="33c80-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33c80-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33c80-109">Requirements</span></span>  

 <span data-ttu-id="33c80-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33c80-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33c80-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="33c80-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="33c80-112">**Biblioteca:** Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="33c80-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="33c80-113">Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="33c80-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="33c80-114">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33c80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c80-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33c80-115">See also</span></span>

- [<span data-ttu-id="33c80-116">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="33c80-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="33c80-117">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="33c80-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="33c80-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="33c80-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
