---
title: "GetHistoryFileDirectory (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d0ec18a4f95d0d280a66b3b9d9200c560f5f187
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="09d0c-102">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="09d0c-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="09d0c-103">Recupera la ruta de acceso del directorio de historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09d0c-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09d0c-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09d0c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09d0c-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="09d0c-106">[out] Un búfer para almacenar la ruta de acceso al directorio de historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09d0c-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="09d0c-107">[entrada, salida] La longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="09d0c-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09d0c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09d0c-108">Return Value</span></span>  
 <span data-ttu-id="09d0c-109">Este método devuelve códigos de error COM estándar, tal como se define en el archivo WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="09d0c-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="09d0c-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="09d0c-110">Return code</span></span>|<span data-ttu-id="09d0c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="09d0c-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="09d0c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="09d0c-112">S_OK</span></span>|<span data-ttu-id="09d0c-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="09d0c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="09d0c-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="09d0c-114">E_INVALIDARG</span></span>|<span data-ttu-id="09d0c-115">`wzDir`o `pdwSize` es nulo o la versión de cadena no es correcta.</span><span class="sxs-lookup"><span data-stu-id="09d0c-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09d0c-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09d0c-116">Remarks</span></span>  
 <span data-ttu-id="09d0c-117">Cuando se finaliza correctamente, el `pdwSize` argumento se establece en la longitud de la cadena de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="09d0c-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09d0c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09d0c-118">Requirements</span></span>  
 <span data-ttu-id="09d0c-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09d0c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d0c-120">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="09d0c-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="09d0c-121">**Biblioteca:** Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="09d0c-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="09d0c-122">Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que la versión correcta de .NET Framework de destino.</span><span class="sxs-lookup"><span data-stu-id="09d0c-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="09d0c-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d0c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d0c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="09d0c-124">See Also</span></span>  
 [<span data-ttu-id="09d0c-125">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="09d0c-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="09d0c-126">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="09d0c-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="09d0c-127">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="09d0c-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
