---
description: 'Más información sobre: ICeeGen:: Getsectionblock ((método)'
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
ms.openlocfilehash: d1a9fdeb35507f9dd6528b581be877049d2a1478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721156"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="030ba-103">ICeeGen::GetSectionBlock (Método)</span><span class="sxs-lookup"><span data-stu-id="030ba-103">ICeeGen::GetSectionBlock Method</span></span>

<span data-ttu-id="030ba-104">Obtiene un bloque de sección del código base.</span><span class="sxs-lookup"><span data-stu-id="030ba-104">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="030ba-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="030ba-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="030ba-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="030ba-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="030ba-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="030ba-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="030ba-108">de La sección de la que se va a recuperar un bloque del código base.</span><span class="sxs-lookup"><span data-stu-id="030ba-108">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="030ba-109">de Longitud del bloque que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="030ba-109">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="030ba-110">de Byte, con respecto al principio de la sección, con el que se va a alinear el primer byte del bloque.</span><span class="sxs-lookup"><span data-stu-id="030ba-110">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="030ba-111">Esta es la posición del bloque dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="030ba-111">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="030ba-112">enuncia Puntero a una ubicación que recibe la dirección del bloque recuperado.</span><span class="sxs-lookup"><span data-stu-id="030ba-112">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="030ba-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="030ba-113">Remarks</span></span>  

 <span data-ttu-id="030ba-114">Llame `GetSectionBlock` solo si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="030ba-114">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="030ba-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="030ba-115">Requirements</span></span>  

 <span data-ttu-id="030ba-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="030ba-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="030ba-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="030ba-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="030ba-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="030ba-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="030ba-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="030ba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="030ba-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="030ba-120">See also</span></span>

- [<span data-ttu-id="030ba-121">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="030ba-121">ICeeGen Interface</span></span>](iceegen-interface.md)
