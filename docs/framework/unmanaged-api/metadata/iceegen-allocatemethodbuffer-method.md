---
description: 'Más información sobre: ICeeGen:: Allocatemethodbuffer ((método)'
title: ICeeGen::AllocateMethodBuffer (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: ced5ac8b4fdd89fc41c2c70b68c5b49843a519e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707168"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="06006-103">ICeeGen::AllocateMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="06006-103">ICeeGen::AllocateMethodBuffer Method</span></span>

<span data-ttu-id="06006-104">Crea un búfer con el tamaño especificado para un método y obtiene la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="06006-104">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="06006-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="06006-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06006-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06006-106">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06006-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06006-107">Parameters</span></span>  

 `cchBuffer`  
 <span data-ttu-id="06006-108">de Longitud del búfer que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="06006-108">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="06006-109">enuncia Búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="06006-109">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="06006-110">enuncia Dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="06006-110">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06006-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06006-111">Requirements</span></span>  

 <span data-ttu-id="06006-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06006-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06006-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06006-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06006-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06006-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06006-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06006-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06006-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="06006-116">See also</span></span>

- [<span data-ttu-id="06006-117">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06006-117">ICeeGen Interface</span></span>](iceegen-interface.md)
