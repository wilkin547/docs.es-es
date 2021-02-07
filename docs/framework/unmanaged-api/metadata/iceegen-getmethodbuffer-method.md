---
description: 'Más información sobre: ICeeGen:: Getmethodbuffer ((método)'
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
ms.openlocfilehash: 24811f231b1db6d985753d4f4695f432aa12edc2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706947"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="45dca-103">ICeeGen::GetMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="45dca-103">ICeeGen::GetMethodBuffer Method</span></span>

<span data-ttu-id="45dca-104">Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="45dca-104">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="45dca-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="45dca-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45dca-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45dca-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45dca-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45dca-107">Parameters</span></span>  

 `RVA`  
 <span data-ttu-id="45dca-108">de Dirección virtual relativa del método para el que se va a devolver un búfer.</span><span class="sxs-lookup"><span data-stu-id="45dca-108">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="45dca-109">enuncia Puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="45dca-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45dca-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45dca-110">Requirements</span></span>  

 <span data-ttu-id="45dca-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45dca-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45dca-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45dca-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45dca-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45dca-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45dca-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45dca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45dca-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="45dca-115">See also</span></span>

- [<span data-ttu-id="45dca-116">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45dca-116">ICeeGen Interface</span></span>](iceegen-interface.md)
