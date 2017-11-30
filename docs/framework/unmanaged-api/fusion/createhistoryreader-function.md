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
ms.openlocfilehash: 4f4b09f592a27b7d3d25b2dbe13be7e261023bf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="145b9-102">CreateHistoryReader (Función)</span><span class="sxs-lookup"><span data-stu-id="145b9-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="145b9-103">Crea un lector de historial para el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="145b9-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="145b9-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="145b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="145b9-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="145b9-106">[in] La ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="145b9-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="145b9-107">[out] Cuando se finaliza correctamente, contiene un puntero al lector de historial.</span><span class="sxs-lookup"><span data-stu-id="145b9-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="145b9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="145b9-108">Return Value</span></span>  
 <span data-ttu-id="145b9-109">Este método devuelve los códigos de error COM estándar definidos en WinError.h, además de los valores descritos en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="145b9-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="145b9-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="145b9-110">Return code</span></span>|<span data-ttu-id="145b9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="145b9-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="145b9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="145b9-112">S_OK</span></span>|<span data-ttu-id="145b9-113">Indica que el método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="145b9-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="145b9-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="145b9-114">E_INVALIDARG</span></span>|<span data-ttu-id="145b9-115">Indica que `wzFilePath` o `ppHistoryReader` se establecen en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="145b9-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="145b9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="145b9-116">Requirements</span></span>  
 <span data-ttu-id="145b9-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="145b9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="145b9-118">**Biblioteca:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="145b9-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="145b9-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="145b9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="145b9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="145b9-120">See Also</span></span>  
 [<span data-ttu-id="145b9-121">Funciones estáticas globales de fusión</span><span class="sxs-lookup"><span data-stu-id="145b9-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
