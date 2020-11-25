---
title: ICeeGen::ComputePointer (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 41a3b9c77fc766b2fa39b406dedbb3203cc97ad9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715477"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="de3c3-102">ICeeGen::ComputePointer (Método)</span><span class="sxs-lookup"><span data-stu-id="de3c3-102">ICeeGen::ComputePointer Method</span></span>

<span data-ttu-id="de3c3-103">Determina el búfer para la sección de código especificada.</span><span class="sxs-lookup"><span data-stu-id="de3c3-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="de3c3-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="de3c3-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3c3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de3c3-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de3c3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de3c3-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="de3c3-107">de La sección de código para la que se va a devolver un búfer.</span><span class="sxs-lookup"><span data-stu-id="de3c3-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="de3c3-108">de Dirección virtual relativa del método para el que se va a obtener un puntero.</span><span class="sxs-lookup"><span data-stu-id="de3c3-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="de3c3-109">enuncia Puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="de3c3-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de3c3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de3c3-110">Requirements</span></span>  

 <span data-ttu-id="de3c3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de3c3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de3c3-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="de3c3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de3c3-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de3c3-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de3c3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de3c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3c3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de3c3-115">See also</span></span>

- [<span data-ttu-id="de3c3-116">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de3c3-116">ICeeGen Interface</span></span>](iceegen-interface.md)
