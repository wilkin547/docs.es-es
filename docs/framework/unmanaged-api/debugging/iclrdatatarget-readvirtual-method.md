---
description: 'Más información acerca de: ICLRDataTarget:: Readvirtual ((método)'
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
ms.openlocfilehash: 740a89c95092cfad7974d6bc708c5d8b0d2a9172
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738213"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="d8305-103">ICLRDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="d8305-103">ICLRDataTarget::ReadVirtual Method</span></span>

<span data-ttu-id="d8305-104">Lee datos de la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="d8305-104">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8305-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8305-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8305-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8305-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="d8305-107">de CLRDATA_ADDRESS que almacena la dirección de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="d8305-107">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="d8305-108">enuncia Un puntero a un búfer que recibe los datos.</span><span class="sxs-lookup"><span data-stu-id="d8305-108">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="d8305-109">de Longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="d8305-109">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="d8305-110">enuncia Puntero al número de bytes devueltos.</span><span class="sxs-lookup"><span data-stu-id="d8305-110">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8305-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8305-111">Requirements</span></span>  

 <span data-ttu-id="d8305-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8305-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8305-113">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="d8305-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d8305-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8305-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8305-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8305-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8305-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8305-116">See also</span></span>

- [<span data-ttu-id="d8305-117">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8305-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
