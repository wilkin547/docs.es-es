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
ms.openlocfilehash: 1aabfad14ee2eb35916bbf115631602276cd1fc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109892"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="fd30c-102">GetHistoryFileDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="fd30c-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="fd30c-103">Recupera la ruta de acceso del directorio del historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd30c-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd30c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd30c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd30c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd30c-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="fd30c-106">enuncia Un búfer que contiene la ruta de acceso al directorio del historial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd30c-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="fd30c-107">[in, out] Longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="fd30c-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd30c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd30c-108">Return Value</span></span>  
 <span data-ttu-id="fd30c-109">Este método devuelve los códigos de error COM estándar, tal y como se define en el archivo WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="fd30c-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="fd30c-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="fd30c-110">Return code</span></span>|<span data-ttu-id="fd30c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd30c-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fd30c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd30c-112">S_OK</span></span>|<span data-ttu-id="fd30c-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd30c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="fd30c-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fd30c-114">E_INVALIDARG</span></span>|<span data-ttu-id="fd30c-115">`wzDir` o `pdwSize` es null, o la cadena de versión es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="fd30c-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd30c-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd30c-116">Remarks</span></span>  
 <span data-ttu-id="fd30c-117">Si se completa correctamente, el argumento `pdwSize` se establece en la longitud de la cadena de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="fd30c-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd30c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd30c-118">Requirements</span></span>  
 <span data-ttu-id="fd30c-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd30c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd30c-120">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fd30c-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fd30c-121">**Biblioteca:** Fusion. dll y mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="fd30c-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="fd30c-122">Use Fusion. dll en lugar de mscorwks. dll para asegurarse de que tiene como destino la versión correcta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd30c-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="fd30c-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd30c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd30c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd30c-124">See also</span></span>

- [<span data-ttu-id="fd30c-125">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="fd30c-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="fd30c-126">NukeDownloadedCache (Función)</span><span class="sxs-lookup"><span data-stu-id="fd30c-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="fd30c-127">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="fd30c-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
