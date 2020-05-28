---
title: ICeeGen::GetMethodBuffer (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
ms.openlocfilehash: 99eef11c294dbb17b30b2ef28e65999d4d60f817
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008337"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="62914-102">ICeeGen::GetMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="62914-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="62914-103">Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="62914-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="62914-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="62914-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62914-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62914-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62914-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62914-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="62914-107">de Dirección virtual relativa del método para el que se va a devolver un búfer.</span><span class="sxs-lookup"><span data-stu-id="62914-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="62914-108">enuncia Puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="62914-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62914-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62914-109">Requirements</span></span>  
 <span data-ttu-id="62914-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62914-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62914-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="62914-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62914-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62914-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62914-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62914-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62914-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62914-114">See also</span></span>

- [<span data-ttu-id="62914-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62914-115">ICeeGen Interface</span></span>](iceegen-interface.md)
