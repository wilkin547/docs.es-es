---
title: "PreBindAssemblyEx (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PreBindAssemblyEx
api_location: fusion.dll
api_type: DLLExport
f1_keywords: PreBindAssemblyEx
helpviewer_keywords: PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05977db8e01d00af6e160cb2993867cf83eb24c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="b9ca4-102">PreBindAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="b9ca4-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="b9ca4-103">Obtiene el nombre para mostrar tras aplicar la directiva de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="b9ca4-104">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ca4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9ca4-105">Syntax</span></span>  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9ca4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9ca4-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="b9ca4-107">[in] Identifica el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="b9ca4-108">[in] Identifica el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="b9ca4-109">[in] Identifica el ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="b9ca4-110">Este parámetro se ignora.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="b9ca4-111">[in] Identifica la versión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="b9ca4-112">[out] Contiene el nombre para mostrar tras aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b9ca4-113">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b9ca4-114">`pvReserved`debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9ca4-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9ca4-115">Remarks</span></span>  
 <span data-ttu-id="b9ca4-116">El `ppNamePostPolicy` parámetro de salida se establece únicamente si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="b9ca4-117">En caso contrario, es null.</span><span class="sxs-lookup"><span data-stu-id="b9ca4-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ca4-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9ca4-118">Requirements</span></span>  
 <span data-ttu-id="b9ca4-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ca4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ca4-120">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b9ca4-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b9ca4-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9ca4-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9ca4-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ca4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ca4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9ca4-123">See Also</span></span>  
 [<span data-ttu-id="b9ca4-124">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="b9ca4-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
