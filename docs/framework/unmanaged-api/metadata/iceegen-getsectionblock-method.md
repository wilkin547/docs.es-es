---
title: "ICeeGen::GetSectionBlock (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionBlock
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4732eef9a47f9ea1e919bd9d855afbec18974454
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="4b822-102">ICeeGen::GetSectionBlock (Método)</span><span class="sxs-lookup"><span data-stu-id="4b822-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="4b822-103">Obtiene un bloque de sección del código base.</span><span class="sxs-lookup"><span data-stu-id="4b822-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="4b822-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="4b822-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b822-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b822-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b822-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b822-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="4b822-107">[in] La sección de la que se va a recuperar un bloque de código base.</span><span class="sxs-lookup"><span data-stu-id="4b822-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="4b822-108">[in] La longitud del bloque que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="4b822-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="4b822-109">[in] El byte, relativa al comienzo de la sección, con el que se va a alinear el primer byte del bloque.</span><span class="sxs-lookup"><span data-stu-id="4b822-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="4b822-110">Esta es la posición del bloque dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="4b822-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="4b822-111">[out] Un puntero a una ubicación que recibe la dirección del bloque recuperado.</span><span class="sxs-lookup"><span data-stu-id="4b822-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b822-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b822-112">Remarks</span></span>  
 <span data-ttu-id="4b822-113">Llame a `GetSectionBlock` sólo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="4b822-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b822-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b822-114">Requirements</span></span>  
 <span data-ttu-id="4b822-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b822-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b822-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b822-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b822-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b822-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b822-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b822-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b822-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b822-119">See Also</span></span>  
 [<span data-ttu-id="4b822-120">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b822-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
