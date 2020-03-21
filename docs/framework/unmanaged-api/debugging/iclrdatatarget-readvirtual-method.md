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
ms.openlocfilehash: 0332fae46d6a65cfb7cc0b929cc2fd0d97e1790e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179158"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="5233d-102">ICLRDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="5233d-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="5233d-103">Lee los datos de la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="5233d-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5233d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5233d-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5233d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5233d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5233d-106">[en] Un CLRDATA_ADDRESS que almacena la dirección de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="5233d-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="5233d-107">[fuera] Puntero a un búfer que recibe los datos.</span><span class="sxs-lookup"><span data-stu-id="5233d-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="5233d-108">[en] La longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="5233d-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="5233d-109">[fuera] Puntero al número de bytes devueltos.</span><span class="sxs-lookup"><span data-stu-id="5233d-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5233d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5233d-110">Requirements</span></span>  
 <span data-ttu-id="5233d-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5233d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5233d-112">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5233d-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5233d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5233d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5233d-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5233d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5233d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5233d-115">See also</span></span>

- [<span data-ttu-id="5233d-116">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5233d-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
