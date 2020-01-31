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
ms.openlocfilehash: 83e2d1231b85086c2e65813cf427df3de36405b7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785310"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="89afc-102">ICLRDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="89afc-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="89afc-103">Lee datos de la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="89afc-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89afc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89afc-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89afc-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="89afc-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="89afc-106">de CLRDATA_ADDRESS que almacena la dirección de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="89afc-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="89afc-107">enuncia Un puntero a un búfer que recibe los datos.</span><span class="sxs-lookup"><span data-stu-id="89afc-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="89afc-108">de Longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="89afc-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="89afc-109">enuncia Puntero al número de bytes devueltos.</span><span class="sxs-lookup"><span data-stu-id="89afc-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89afc-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="89afc-110">Requirements</span></span>  
 <span data-ttu-id="89afc-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89afc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89afc-112">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="89afc-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="89afc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89afc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89afc-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89afc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89afc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="89afc-115">See also</span></span>

- [<span data-ttu-id="89afc-116">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89afc-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
