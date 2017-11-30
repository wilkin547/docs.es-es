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
ms.openlocfilehash: c1f5f1c0ea5672812fca387b34238ada2a109938
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="cb7f9-102">ICeeGen::ComputePointer (Método)</span><span class="sxs-lookup"><span data-stu-id="cb7f9-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="cb7f9-103">Determina el búfer para la sección de código especificada.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="cb7f9-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb7f9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb7f9-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb7f9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb7f9-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="cb7f9-107">[in] La sección de código para el que se va a devolver el búfer.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="cb7f9-108">[in] La dirección virtual relativa del método para el que se va a obtener un puntero.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="cb7f9-109">[out] Un puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="cb7f9-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb7f9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb7f9-110">Requirements</span></span>  
 <span data-ttu-id="cb7f9-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb7f9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb7f9-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cb7f9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb7f9-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb7f9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb7f9-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb7f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7f9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb7f9-115">See Also</span></span>  
 [<span data-ttu-id="cb7f9-116">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb7f9-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
