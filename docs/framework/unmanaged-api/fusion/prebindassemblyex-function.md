---
description: 'Más información acerca de: Prebindassemblyex ((función)'
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
ms.openlocfilehash: e94bd7c335555e8109df60a00cadc76f7e13434b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800011"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="759d0-103">PreBindAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="759d0-103">PreBindAssemblyEx Function</span></span>

<span data-ttu-id="759d0-104">Obtiene el nombre para mostrar de la Directiva posterior de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="759d0-104">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="759d0-105">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="759d0-105">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759d0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="759d0-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="759d0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="759d0-107">Parameters</span></span>  

 `pAppCtx`  
 <span data-ttu-id="759d0-108">de Identifica el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="759d0-108">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="759d0-109">de Identifica el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="759d0-109">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="759d0-110">de Identifica el ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="759d0-110">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="759d0-111">Este parámetro se ignora.</span><span class="sxs-lookup"><span data-stu-id="759d0-111">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="759d0-112">de Identifica la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="759d0-112">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="759d0-113">enuncia Contiene el nombre para mostrar de la Directiva posterior.</span><span class="sxs-lookup"><span data-stu-id="759d0-113">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="759d0-114">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="759d0-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="759d0-115">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="759d0-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="759d0-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="759d0-116">Remarks</span></span>  

 <span data-ttu-id="759d0-117">El `ppNamePostPolicy` parámetro de salida se establece solo si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="759d0-117">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="759d0-118">En caso contrario, es null.</span><span class="sxs-lookup"><span data-stu-id="759d0-118">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="759d0-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="759d0-119">Requirements</span></span>  

 <span data-ttu-id="759d0-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="759d0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="759d0-121">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="759d0-121">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="759d0-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="759d0-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="759d0-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="759d0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759d0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="759d0-124">See also</span></span>

- [<span data-ttu-id="759d0-125">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="759d0-125">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
