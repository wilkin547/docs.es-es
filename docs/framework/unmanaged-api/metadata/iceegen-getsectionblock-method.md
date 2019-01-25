---
title: ICeeGen::GetSectionBlock (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb1268d9fd892a4400491aca7966d81a3e23f9c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515357"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="99ff4-102">ICeeGen::GetSectionBlock (Método)</span><span class="sxs-lookup"><span data-stu-id="99ff4-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="99ff4-103">Obtiene un bloque de sección del código base.</span><span class="sxs-lookup"><span data-stu-id="99ff4-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="99ff4-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="99ff4-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ff4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99ff4-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="99ff4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99ff4-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="99ff4-107">[in] La sección desde el que se va a recuperar un bloque de la base de código.</span><span class="sxs-lookup"><span data-stu-id="99ff4-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="99ff4-108">[in] La longitud del bloque que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="99ff4-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="99ff4-109">[in] El byte, con respecto al principio de la sección con la que se va a alinear el primer byte del bloque.</span><span class="sxs-lookup"><span data-stu-id="99ff4-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="99ff4-110">Esta es la posición del bloque dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="99ff4-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="99ff4-111">[out] Un puntero a una ubicación que recibe la dirección del bloque recuperado.</span><span class="sxs-lookup"><span data-stu-id="99ff4-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99ff4-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99ff4-112">Remarks</span></span>  
 <span data-ttu-id="99ff4-113">Llamar a `GetSectionBlock` sólo si tiene requisitos de sección especial que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="99ff4-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ff4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99ff4-114">Requirements</span></span>  
 <span data-ttu-id="99ff4-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99ff4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ff4-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="99ff4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99ff4-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99ff4-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99ff4-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ff4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ff4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ff4-119">See also</span></span>
- [<span data-ttu-id="99ff4-120">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99ff4-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
