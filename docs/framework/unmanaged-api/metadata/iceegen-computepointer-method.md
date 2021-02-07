---
description: 'Más información sobre: ICeeGen:: Computepointer ((método)'
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
ms.openlocfilehash: 9319343cc93eae3e4c7b060239d23ad8aeb7d3e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721182"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="02ddc-103">ICeeGen::ComputePointer (Método)</span><span class="sxs-lookup"><span data-stu-id="02ddc-103">ICeeGen::ComputePointer Method</span></span>

<span data-ttu-id="02ddc-104">Determina el búfer para la sección de código especificada.</span><span class="sxs-lookup"><span data-stu-id="02ddc-104">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="02ddc-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="02ddc-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ddc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02ddc-106">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02ddc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02ddc-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="02ddc-108">de La sección de código para la que se va a devolver un búfer.</span><span class="sxs-lookup"><span data-stu-id="02ddc-108">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="02ddc-109">de Dirección virtual relativa del método para el que se va a obtener un puntero.</span><span class="sxs-lookup"><span data-stu-id="02ddc-109">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="02ddc-110">enuncia Puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="02ddc-110">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ddc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02ddc-111">Requirements</span></span>  

 <span data-ttu-id="02ddc-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02ddc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ddc-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="02ddc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02ddc-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02ddc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02ddc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ddc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ddc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="02ddc-116">See also</span></span>

- [<span data-ttu-id="02ddc-117">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02ddc-117">ICeeGen Interface</span></span>](iceegen-interface.md)
