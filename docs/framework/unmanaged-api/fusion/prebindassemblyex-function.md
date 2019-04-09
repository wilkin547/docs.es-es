---
title: PreBindAssemblyEx (Función)
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8251d21fe535f85cc6abd0a7bc6c96ab320007f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090243"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="901b8-102">PreBindAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="901b8-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="901b8-103">Obtiene el nombre para mostrar tras aplicar la directiva para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="901b8-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="901b8-104">Esta función admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="901b8-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="901b8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="901b8-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="901b8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="901b8-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="901b8-107">[in] Identifica el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="901b8-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="901b8-108">[in] Identifica el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="901b8-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="901b8-109">[in] Identifica el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="901b8-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="901b8-110">Este parámetro se ignora.</span><span class="sxs-lookup"><span data-stu-id="901b8-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="901b8-111">[in] Identifica la versión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="901b8-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="901b8-112">[out] Contiene el nombre para mostrar tras aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="901b8-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="901b8-113">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="901b8-113">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="901b8-114">debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="901b8-114">must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="901b8-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="901b8-115">Remarks</span></span>  
 <span data-ttu-id="901b8-116">El `ppNamePostPolicy` parámetro de salida se establece únicamente si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="901b8-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="901b8-117">En caso contrario, es null.</span><span class="sxs-lookup"><span data-stu-id="901b8-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="901b8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="901b8-118">Requirements</span></span>  
 <span data-ttu-id="901b8-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="901b8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="901b8-120">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="901b8-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="901b8-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="901b8-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="901b8-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="901b8-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="901b8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="901b8-123">See also</span></span>

- [<span data-ttu-id="901b8-124">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="901b8-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
