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
ms.openlocfilehash: 79ef272e0c8afa0cd1942416c3a5eb9b825c2e6f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145150"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="89d46-102">ICeeGen::ComputePointer (Método)</span><span class="sxs-lookup"><span data-stu-id="89d46-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="89d46-103">Determina el búfer para la sección de códigos especificada.</span><span class="sxs-lookup"><span data-stu-id="89d46-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="89d46-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="89d46-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d46-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89d46-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89d46-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89d46-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="89d46-107">[in] La sección de código que se va a devolver el búfer.</span><span class="sxs-lookup"><span data-stu-id="89d46-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="89d46-108">[in] La dirección virtual relativa del método para que se va a obtener un puntero.</span><span class="sxs-lookup"><span data-stu-id="89d46-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="89d46-109">[out] Un puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="89d46-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d46-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89d46-110">Requirements</span></span>  
 <span data-ttu-id="89d46-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89d46-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d46-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="89d46-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89d46-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89d46-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89d46-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d46-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d46-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="89d46-115">See also</span></span>

- [<span data-ttu-id="89d46-116">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89d46-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
