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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 496082bbf89ceb93ba3dceef9a9222425db71784
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522419"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="0f2f0-102">ICeeGen::ComputePointer (Método)</span><span class="sxs-lookup"><span data-stu-id="0f2f0-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="0f2f0-103">Determina el búfer para la sección de códigos especificada.</span><span class="sxs-lookup"><span data-stu-id="0f2f0-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="0f2f0-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="0f2f0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f2f0-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f2f0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f2f0-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0f2f0-107">[in] La sección de código que se va a devolver el búfer.</span><span class="sxs-lookup"><span data-stu-id="0f2f0-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="0f2f0-108">[in] La dirección virtual relativa del método para que se va a obtener un puntero.</span><span class="sxs-lookup"><span data-stu-id="0f2f0-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="0f2f0-109">[out] Un puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="0f2f0-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f2f0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f2f0-110">Requirements</span></span>  
 <span data-ttu-id="0f2f0-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f2f0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f2f0-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f2f0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f2f0-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f2f0-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f2f0-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f2f0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2f0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f2f0-115">See also</span></span>
- [<span data-ttu-id="0f2f0-116">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f2f0-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
