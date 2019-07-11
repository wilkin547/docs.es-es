---
title: GetHistoryFileDirectory (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10eead2772a2bbd8abaf7b9c090a091687725972
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778652"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="621dc-102">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="621dc-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="621dc-103">Recupera la ruta de acceso del directorio de historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="621dc-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="621dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="621dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="621dc-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="621dc-106">[out] Un búfer para almacenar la ruta de acceso al directorio de historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="621dc-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="621dc-107">[in, out] La longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="621dc-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="621dc-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="621dc-108">Return Value</span></span>  
 <span data-ttu-id="621dc-109">Este método devuelve códigos de error COM estándar, tal como se define en el archivo WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="621dc-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="621dc-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="621dc-110">Return code</span></span>|<span data-ttu-id="621dc-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="621dc-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="621dc-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="621dc-112">S_OK</span></span>|<span data-ttu-id="621dc-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="621dc-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="621dc-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="621dc-114">E_INVALIDARG</span></span>|<span data-ttu-id="621dc-115">`wzDir` o `pdwSize` es null, o la versión de cadena no es correcta.</span><span class="sxs-lookup"><span data-stu-id="621dc-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="621dc-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="621dc-116">Remarks</span></span>  
 <span data-ttu-id="621dc-117">Se completa correctamente, el `pdwSize` argumento está establecido en la longitud de la cadena de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="621dc-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621dc-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="621dc-118">Requirements</span></span>  
 <span data-ttu-id="621dc-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="621dc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="621dc-120">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="621dc-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="621dc-121">**Biblioteca:** El archivo Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="621dc-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="621dc-122">Use el archivo Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="621dc-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="621dc-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="621dc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621dc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="621dc-124">See also</span></span>

- [<span data-ttu-id="621dc-125">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="621dc-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="621dc-126">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="621dc-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [<span data-ttu-id="621dc-127">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="621dc-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
