---
description: 'Más información acerca de: GetHistoryFileDirectory ((función)'
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
ms.openlocfilehash: 960bc75d69f4be6d1639e109d6327b5e65d3e129
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760971"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="cb8f6-103">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="cb8f6-103">GetHistoryFileDirectory Function</span></span>

<span data-ttu-id="cb8f6-104">Recupera la ruta de acceso del directorio del historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-104">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb8f6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb8f6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb8f6-106">Parameters</span></span>  

 `wzDir`  
 <span data-ttu-id="cb8f6-107">enuncia Un búfer que contiene la ruta de acceso al directorio del historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-107">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="cb8f6-108">[in, out] Longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-108">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb8f6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cb8f6-109">Return Value</span></span>  

 <span data-ttu-id="cb8f6-110">Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-110">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="cb8f6-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="cb8f6-111">Return code</span></span>|<span data-ttu-id="cb8f6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb8f6-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cb8f6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb8f6-113">S_OK</span></span>|<span data-ttu-id="cb8f6-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="cb8f6-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cb8f6-115">E_INVALIDARG</span></span>|<span data-ttu-id="cb8f6-116">`wzDir` o `pdwSize` es null, o la cadena de versión es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-116">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb8f6-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb8f6-117">Remarks</span></span>  

 <span data-ttu-id="cb8f6-118">Si se completa correctamente, el `pdwSize` argumento se establece en la longitud de la cadena de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-118">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb8f6-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb8f6-119">Requirements</span></span>  

 <span data-ttu-id="cb8f6-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb8f6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb8f6-121">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cb8f6-121">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cb8f6-122">**Biblioteca:** Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-122">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="cb8f6-123">Use Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tiene como destino la versión correcta de la .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb8f6-123">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cb8f6-124">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb8f6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8f6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb8f6-125">See also</span></span>

- [<span data-ttu-id="cb8f6-126">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="cb8f6-126">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="cb8f6-127">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="cb8f6-127">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="cb8f6-128">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="cb8f6-128">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
