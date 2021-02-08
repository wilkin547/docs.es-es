---
description: 'Más información acerca de: ICLRDataTarget:: WriteVirtual ((método)'
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
ms.openlocfilehash: 29ff8d629c5797099dab155802fff99786f4ce15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794863"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="a7848-103">ICLRDataTarget::WriteVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="a7848-103">ICLRDataTarget::WriteVirtual Method</span></span>

<span data-ttu-id="a7848-104">Escribe datos del búfer especificado en la dirección de memoria virtual especificada.</span><span class="sxs-lookup"><span data-stu-id="a7848-104">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7848-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7848-105">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7848-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7848-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="a7848-107">de CLRDATA_ADDRESS que almacena la dirección de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="a7848-107">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a7848-108">de Puntero a un búfer que almacena los datos que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="a7848-108">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="a7848-109">de Número de bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="a7848-109">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="a7848-110">enuncia Puntero al número real de bytes que se escribieron.</span><span class="sxs-lookup"><span data-stu-id="a7848-110">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7848-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7848-111">Requirements</span></span>  

 <span data-ttu-id="a7848-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7848-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7848-113">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="a7848-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a7848-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7848-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7848-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7848-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7848-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7848-116">See also</span></span>

- [<span data-ttu-id="a7848-117">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7848-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
