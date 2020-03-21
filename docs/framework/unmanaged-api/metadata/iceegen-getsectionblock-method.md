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
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176089"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="dd26a-102">ICeeGen::GetSectionBlock (Método)</span><span class="sxs-lookup"><span data-stu-id="dd26a-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="dd26a-103">Obtiene un bloque de sección de la base de código.</span><span class="sxs-lookup"><span data-stu-id="dd26a-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="dd26a-104">Este método está obsoleto y no se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="dd26a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd26a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd26a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="dd26a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd26a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="dd26a-107">[en] La sección desde la que se va a recuperar un bloque de la base de código.</span><span class="sxs-lookup"><span data-stu-id="dd26a-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="dd26a-108">[en] La longitud del bloque que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="dd26a-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="dd26a-109">[en] El byte, relativo al principio de la sección, con el que alinear el primer byte del bloque.</span><span class="sxs-lookup"><span data-stu-id="dd26a-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="dd26a-110">Esta es la posición del bloque dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="dd26a-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="dd26a-111">[fuera] Puntero a una ubicación que recibe la dirección del bloque recuperado.</span><span class="sxs-lookup"><span data-stu-id="dd26a-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd26a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dd26a-112">Remarks</span></span>  
 <span data-ttu-id="dd26a-113">Llame `GetSectionBlock` solamente si usted tiene los requisitos de la sección especial que no son manejados por otros métodos.</span><span class="sxs-lookup"><span data-stu-id="dd26a-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd26a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd26a-114">Requirements</span></span>  
 <span data-ttu-id="dd26a-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd26a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd26a-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd26a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd26a-117">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd26a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd26a-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd26a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd26a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd26a-119">See also</span></span>

- [<span data-ttu-id="dd26a-120">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd26a-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
