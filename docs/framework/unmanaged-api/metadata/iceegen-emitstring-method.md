---
description: 'Más información sobre: ICeeGen:: Emitstring ((método)'
title: ICeeGen::EmitString (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: fca388d044603f932bf90a176cada6e830284702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707116"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="5a576-103">ICeeGen::EmitString (Método)</span><span class="sxs-lookup"><span data-stu-id="5a576-103">ICeeGen::EmitString Method</span></span>

<span data-ttu-id="5a576-104">Emite la cadena especificada en el código base.</span><span class="sxs-lookup"><span data-stu-id="5a576-104">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="5a576-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="5a576-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a576-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a576-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a576-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a576-107">Parameters</span></span>  

 `lpString`  
 <span data-ttu-id="5a576-108">de Cadena que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="5a576-108">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="5a576-109">enuncia Dirección virtual relativa de la cadena emitida.</span><span class="sxs-lookup"><span data-stu-id="5a576-109">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a576-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a576-110">Requirements</span></span>  

 <span data-ttu-id="5a576-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a576-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a576-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5a576-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a576-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a576-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a576-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a576-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a576-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a576-115">See also</span></span>

- [<span data-ttu-id="5a576-116">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a576-116">ICeeGen Interface</span></span>](iceegen-interface.md)
