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
ms.openlocfilehash: db3ba3380d1fc30a8f34683618b5cc326d7d1906
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123060"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="41d3a-102">PreBindAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="41d3a-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="41d3a-103">Obtiene el nombre para mostrar de la Directiva posterior de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41d3a-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="41d3a-104">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="41d3a-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41d3a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41d3a-105">Syntax</span></span>  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="41d3a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41d3a-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="41d3a-107">de Identifica el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41d3a-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="41d3a-108">de Identifica el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="41d3a-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="41d3a-109">de Identifica el ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="41d3a-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="41d3a-110">Este parámetro se ignora.</span><span class="sxs-lookup"><span data-stu-id="41d3a-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="41d3a-111">de Identifica la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="41d3a-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="41d3a-112">enuncia Contiene el nombre para mostrar de la Directiva posterior.</span><span class="sxs-lookup"><span data-stu-id="41d3a-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="41d3a-113">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="41d3a-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="41d3a-114">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="41d3a-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41d3a-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41d3a-115">Remarks</span></span>  
 <span data-ttu-id="41d3a-116">El parámetro de salida `ppNamePostPolicy` se establece solo si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="41d3a-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="41d3a-117">De lo contrario, es NULL.</span><span class="sxs-lookup"><span data-stu-id="41d3a-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41d3a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41d3a-118">Requirements</span></span>  
 <span data-ttu-id="41d3a-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41d3a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41d3a-120">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="41d3a-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="41d3a-121">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="41d3a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41d3a-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41d3a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d3a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="41d3a-123">See also</span></span>

- [<span data-ttu-id="41d3a-124">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="41d3a-124">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
