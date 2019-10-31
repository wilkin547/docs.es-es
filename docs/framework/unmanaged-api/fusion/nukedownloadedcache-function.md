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
ms.openlocfilehash: 8f97614412eb2d49b202e86bdabc727159deb5d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131698"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="275da-102">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="275da-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="275da-103">Elimina la memoria caché de descarga del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="275da-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="275da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="275da-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="275da-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="275da-105">Return Value</span></span>  
 <span data-ttu-id="275da-106">Este método devuelve los códigos de error COM estándar, tal y como se define en WinError. h.</span><span class="sxs-lookup"><span data-stu-id="275da-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="275da-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="275da-107">Remarks</span></span>  
 <span data-ttu-id="275da-108">La caché de descarga de CLR es el área donde se almacenan los ensamblados con nombre seguro que se descargan de una dirección URL para poder reutilizarlos.</span><span class="sxs-lookup"><span data-stu-id="275da-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="275da-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="275da-109">Requirements</span></span>  
 <span data-ttu-id="275da-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="275da-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="275da-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="275da-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="275da-112">**Biblioteca:** Fusion. dll y mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="275da-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="275da-113">Use Fusion. dll en lugar de mscorwks. dll para asegurarse de que tiene como destino la versión correcta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="275da-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="275da-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="275da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275da-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="275da-115">See also</span></span>

- [<span data-ttu-id="275da-116">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="275da-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="275da-117">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="275da-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="275da-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="275da-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
