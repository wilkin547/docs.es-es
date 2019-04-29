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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778045"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="b98f3-102">PreBindAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="b98f3-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="b98f3-103">Obtiene el nombre para mostrar tras aplicar la directiva para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="b98f3-104">Esta función admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="b98f3-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98f3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b98f3-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b98f3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b98f3-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="b98f3-107">[in] Identifica el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b98f3-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="b98f3-108">[in] Identifica el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b98f3-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="b98f3-109">[in] Identifica el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="b98f3-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="b98f3-110">Este parámetro se ignora.</span><span class="sxs-lookup"><span data-stu-id="b98f3-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="b98f3-111">[in] Identifica la versión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b98f3-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="b98f3-112">[out] Contiene el nombre para mostrar tras aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="b98f3-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b98f3-113">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="b98f3-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b98f3-114">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="b98f3-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b98f3-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b98f3-115">Remarks</span></span>  
 <span data-ttu-id="b98f3-116">El `ppNamePostPolicy` parámetro de salida se establece únicamente si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="b98f3-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="b98f3-117">En caso contrario, es null.</span><span class="sxs-lookup"><span data-stu-id="b98f3-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b98f3-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b98f3-118">Requirements</span></span>  
 <span data-ttu-id="b98f3-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b98f3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98f3-120">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b98f3-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b98f3-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b98f3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b98f3-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b98f3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98f3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b98f3-123">See also</span></span>

- [<span data-ttu-id="b98f3-124">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="b98f3-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
