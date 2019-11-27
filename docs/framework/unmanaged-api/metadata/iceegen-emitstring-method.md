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
ms.openlocfilehash: 8433ff6e0ec550d6b0558bfb9c7698c49e98278c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436386"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="160e1-102">ICeeGen::EmitString (Método)</span><span class="sxs-lookup"><span data-stu-id="160e1-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="160e1-103">Emite la cadena especificada en el código base.</span><span class="sxs-lookup"><span data-stu-id="160e1-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="160e1-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="160e1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="160e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="160e1-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="160e1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="160e1-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="160e1-107">de Cadena que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="160e1-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="160e1-108">enuncia Dirección virtual relativa de la cadena emitida.</span><span class="sxs-lookup"><span data-stu-id="160e1-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="160e1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="160e1-109">Requirements</span></span>  
 <span data-ttu-id="160e1-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="160e1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="160e1-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="160e1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="160e1-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="160e1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="160e1-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="160e1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160e1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="160e1-114">See also</span></span>

- [<span data-ttu-id="160e1-115">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="160e1-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
