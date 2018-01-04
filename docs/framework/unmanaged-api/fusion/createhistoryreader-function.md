---
title: "CreateHistoryReader (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab5e54735c360cb7bd2e681c04b0b1ae491bd716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="c2e69-102">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="c2e69-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="c2e69-103">Crea un lector de historial para el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c2e69-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2e69-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2e69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2e69-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="c2e69-106">[in] La ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="c2e69-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="c2e69-107">[out] Cuando se finaliza correctamente, contiene un puntero al lector de historial.</span><span class="sxs-lookup"><span data-stu-id="c2e69-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2e69-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2e69-108">Return Value</span></span>  
 <span data-ttu-id="c2e69-109">Este método devuelve los códigos de error COM estándar definidos en WinError.h, además de los valores descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="c2e69-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="c2e69-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="c2e69-110">Return code</span></span>|<span data-ttu-id="c2e69-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2e69-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c2e69-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2e69-112">S_OK</span></span>|<span data-ttu-id="c2e69-113">Indica que el método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2e69-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="c2e69-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c2e69-114">E_INVALIDARG</span></span>|<span data-ttu-id="c2e69-115">Indica que `wzFilePath` o `ppHistoryReader` se establecen en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="c2e69-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2e69-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2e69-116">Requirements</span></span>  
 <span data-ttu-id="c2e69-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2e69-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e69-118">**Biblioteca:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="c2e69-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="c2e69-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2e69-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e69-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2e69-120">See Also</span></span>  
 [<span data-ttu-id="c2e69-121">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="c2e69-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
