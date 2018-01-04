---
title: "ICeeGen::ComputePointer (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.ComputePointer
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b027615f7697b9ea103d44bea0ec44834fe3f04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="62225-102">ICeeGen::ComputePointer (Método)</span><span class="sxs-lookup"><span data-stu-id="62225-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="62225-103">Determina el búfer para la sección de código especificada.</span><span class="sxs-lookup"><span data-stu-id="62225-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="62225-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="62225-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62225-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62225-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62225-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62225-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="62225-107">[in] La sección de código para el que se va a devolver el búfer.</span><span class="sxs-lookup"><span data-stu-id="62225-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="62225-108">[in] La dirección virtual relativa del método para el que se va a obtener un puntero.</span><span class="sxs-lookup"><span data-stu-id="62225-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="62225-109">[out] Un puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="62225-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62225-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62225-110">Requirements</span></span>  
 <span data-ttu-id="62225-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62225-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62225-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="62225-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62225-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62225-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62225-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62225-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62225-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="62225-115">See Also</span></span>  
 [<span data-ttu-id="62225-116">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62225-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
