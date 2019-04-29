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
ms.openlocfilehash: 4e549e13c0d51e4aa708a674a2224168ab66f8ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774535"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="3f32a-102">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="3f32a-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="3f32a-103">Elimina la caché de descarga de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3f32a-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f32a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f32a-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3f32a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f32a-105">Return Value</span></span>  
 <span data-ttu-id="3f32a-106">Este método devuelve códigos de error COM estándar, tal como se define en WinError.h.</span><span class="sxs-lookup"><span data-stu-id="3f32a-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f32a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f32a-107">Remarks</span></span>  
 <span data-ttu-id="3f32a-108">La caché de descarga CLR es el área donde se almacenan los ensamblados con nombre seguro que se descargan desde una dirección URL para una posible reutilización.</span><span class="sxs-lookup"><span data-stu-id="3f32a-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f32a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f32a-109">Requirements</span></span>  
 <span data-ttu-id="3f32a-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f32a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f32a-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3f32a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3f32a-112">**Biblioteca:** El archivo Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="3f32a-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="3f32a-113">Use el archivo Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f32a-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3f32a-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f32a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f32a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f32a-115">See also</span></span>

- [<span data-ttu-id="3f32a-116">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="3f32a-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="3f32a-117">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="3f32a-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="3f32a-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="3f32a-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
