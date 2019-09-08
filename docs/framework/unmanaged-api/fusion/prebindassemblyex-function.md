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
ms.openlocfilehash: 8aa2d174200db76f5c7a6db43e14bb6904604226
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796331"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="8052c-102">PreBindAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="8052c-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="8052c-103">Obtiene el nombre para mostrar de la Directiva posterior de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8052c-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="8052c-104">Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="8052c-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8052c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8052c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8052c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8052c-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="8052c-107">de Identifica el contexto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8052c-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="8052c-108">de Identifica el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8052c-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="8052c-109">de Identifica el ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="8052c-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="8052c-110">Este parámetro se ignora.</span><span class="sxs-lookup"><span data-stu-id="8052c-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="8052c-111">de Identifica la versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8052c-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="8052c-112">enuncia Contiene el nombre para mostrar de la Directiva posterior.</span><span class="sxs-lookup"><span data-stu-id="8052c-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8052c-113">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="8052c-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8052c-114">`pvReserved`debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="8052c-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8052c-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8052c-115">Remarks</span></span>  
 <span data-ttu-id="8052c-116">El `ppNamePostPolicy` parámetro de salida se establece solo si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH.</span><span class="sxs-lookup"><span data-stu-id="8052c-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="8052c-117">De lo contrario, es NULL.</span><span class="sxs-lookup"><span data-stu-id="8052c-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8052c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8052c-118">Requirements</span></span>  
 <span data-ttu-id="8052c-119">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8052c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8052c-120">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8052c-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8052c-121">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8052c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8052c-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8052c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8052c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8052c-123">See also</span></span>

- [<span data-ttu-id="8052c-124">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="8052c-124">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
