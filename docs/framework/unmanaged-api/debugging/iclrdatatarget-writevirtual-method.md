---
title: ICLRDataTarget::WriteVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: 4382d3c9f69df2808f8cd0aaf7f8eaf19bc9891e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793676"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="c9ebb-102">ICLRDataTarget::WriteVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="c9ebb-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="c9ebb-103">Escribe datos del búfer especificado en la dirección de memoria virtual especificada.</span><span class="sxs-lookup"><span data-stu-id="c9ebb-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9ebb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9ebb-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9ebb-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c9ebb-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c9ebb-106">de CLRDATA_ADDRESS que almacena la dirección de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="c9ebb-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c9ebb-107">de Puntero a un búfer que almacena los datos que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="c9ebb-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="c9ebb-108">de Número de bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="c9ebb-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="c9ebb-109">enuncia Puntero al número real de bytes que se escribieron.</span><span class="sxs-lookup"><span data-stu-id="c9ebb-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9ebb-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c9ebb-110">Requirements</span></span>  
 <span data-ttu-id="c9ebb-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9ebb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9ebb-112">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c9ebb-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c9ebb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9ebb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9ebb-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9ebb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ebb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9ebb-115">See also</span></span>

- [<span data-ttu-id="c9ebb-116">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9ebb-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
