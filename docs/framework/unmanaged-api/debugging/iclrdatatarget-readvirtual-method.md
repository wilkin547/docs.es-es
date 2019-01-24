---
title: ICLRDataTarget::ReadVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5484f8bd5515d3a4a3cd08110cc5d48c4356a9f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590151"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="418d5-102">ICLRDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="418d5-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="418d5-103">Lee datos desde la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="418d5-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="418d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="418d5-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="418d5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="418d5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="418d5-106">[in] CLRDATA_ADDRESS que almacena la dirección de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="418d5-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="418d5-107">[out] Un puntero a un búfer que recibe los datos.</span><span class="sxs-lookup"><span data-stu-id="418d5-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="418d5-108">[in] La longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="418d5-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="418d5-109">[out] Devuelve un puntero al número de bytes.</span><span class="sxs-lookup"><span data-stu-id="418d5-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="418d5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="418d5-110">Requirements</span></span>  
 <span data-ttu-id="418d5-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="418d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="418d5-112">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="418d5-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="418d5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="418d5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="418d5-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="418d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418d5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="418d5-115">See also</span></span>
- [<span data-ttu-id="418d5-116">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="418d5-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
