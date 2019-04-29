---
title: ICLRDataTarget::SetTLSValue (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c0be35772b10d89f90da5b33f47aa781034b13a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698088"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="c61b5-102">ICLRDataTarget::SetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="c61b5-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="c61b5-103">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c61b5-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="c61b5-104">Este método llama a los servicios de acceso de datos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c61b5-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c61b5-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c61b5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c61b5-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c61b5-107">[in] El identificador del sistema operativo de un subproceso del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c61b5-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="c61b5-108">[in] El índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="c61b5-108">[in] The index of the location.</span></span> <span data-ttu-id="c61b5-109">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="c61b5-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="c61b5-110">[in] Un `CLRDATA_ADDRESS` valor que especifica el valor se debe colocar en la ubicación especificada de TLS.</span><span class="sxs-lookup"><span data-stu-id="c61b5-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c61b5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c61b5-111">Remarks</span></span>  
 <span data-ttu-id="c61b5-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="c61b5-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c61b5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c61b5-113">Requirements</span></span>  
 <span data-ttu-id="c61b5-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c61b5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c61b5-115">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c61b5-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c61b5-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c61b5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c61b5-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c61b5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c61b5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c61b5-118">See also</span></span>

- [<span data-ttu-id="c61b5-119">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c61b5-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
