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
ms.openlocfilehash: 9587bbe8f087fd9a51bba67492af1d5acb53ae4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176102"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="60487-102">ICeeGen::ComputePointer (Método)</span><span class="sxs-lookup"><span data-stu-id="60487-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="60487-103">Determina el búfer para la sección de código especificada.</span><span class="sxs-lookup"><span data-stu-id="60487-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="60487-104">Este método está obsoleto y no se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="60487-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60487-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60487-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60487-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60487-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="60487-107">[en] La sección de código para la que se va a devolver un búfer.</span><span class="sxs-lookup"><span data-stu-id="60487-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="60487-108">[en] La dirección virtual relativa del método para el que se obtiene un puntero.</span><span class="sxs-lookup"><span data-stu-id="60487-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="60487-109">[fuera] Un puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="60487-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60487-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60487-110">Requirements</span></span>  
 <span data-ttu-id="60487-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60487-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60487-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="60487-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60487-113">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60487-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60487-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60487-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60487-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60487-115">See also</span></span>

- [<span data-ttu-id="60487-116">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60487-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
