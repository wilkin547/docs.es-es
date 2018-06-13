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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e55bc18c7a41e235d1ba6274067c45c26dc7262a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405465"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="89c80-102">ICLRDataTarget::WriteVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="89c80-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="89c80-103">Escribe datos desde el búfer especificado en la dirección de memoria virtual especificada.</span><span class="sxs-lookup"><span data-stu-id="89c80-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89c80-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89c80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89c80-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="89c80-106">[in] CLRDATA_ADDRESS que almacena la dirección de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="89c80-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="89c80-107">[in] Un puntero a un búfer que almacena los datos que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="89c80-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="89c80-108">[in] El número de bytes que se escribirán.</span><span class="sxs-lookup"><span data-stu-id="89c80-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="89c80-109">[out] Un puntero al número real de bytes escritos.</span><span class="sxs-lookup"><span data-stu-id="89c80-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89c80-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89c80-110">Requirements</span></span>  
 <span data-ttu-id="89c80-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89c80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c80-112">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="89c80-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="89c80-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89c80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89c80-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c80-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="89c80-115">See Also</span></span>  
 [<span data-ttu-id="89c80-116">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89c80-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
