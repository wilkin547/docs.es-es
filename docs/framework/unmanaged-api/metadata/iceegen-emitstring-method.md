---
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
ms.openlocfilehash: e7c58e6cdbe0d3c8513721a40eaa3fdfcec6ce2e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008864"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="b69c0-102">ICeeGen::EmitString (Método)</span><span class="sxs-lookup"><span data-stu-id="b69c0-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="b69c0-103">Emite la cadena especificada en el código base.</span><span class="sxs-lookup"><span data-stu-id="b69c0-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="b69c0-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="b69c0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b69c0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b69c0-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b69c0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b69c0-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="b69c0-107">de Cadena que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="b69c0-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="b69c0-108">enuncia Dirección virtual relativa de la cadena emitida.</span><span class="sxs-lookup"><span data-stu-id="b69c0-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b69c0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b69c0-109">Requirements</span></span>  
 <span data-ttu-id="b69c0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b69c0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b69c0-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b69c0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b69c0-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b69c0-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b69c0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b69c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69c0-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b69c0-114">See also</span></span>

- [<span data-ttu-id="b69c0-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b69c0-115">ICeeGen Interface</span></span>](iceegen-interface.md)
