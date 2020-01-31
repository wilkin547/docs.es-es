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
ms.openlocfilehash: 6e6e157c7176a0f4f1ad3c585977e2cfb31c33d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793682"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="d5213-102">ICLRDataTarget::SetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="d5213-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="d5213-103">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d5213-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="d5213-104">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="d5213-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5213-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5213-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5213-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="d5213-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d5213-107">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d5213-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="d5213-108">de Índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="d5213-108">[in] The index of the location.</span></span> <span data-ttu-id="d5213-109">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="d5213-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="d5213-110">de `CLRDATA_ADDRESS` valor que especifica el valor que se va a colocar en la ubicación TLS determinada.</span><span class="sxs-lookup"><span data-stu-id="d5213-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5213-111">Notas</span><span class="sxs-lookup"><span data-stu-id="d5213-111">Remarks</span></span>  
 <span data-ttu-id="d5213-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="d5213-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5213-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d5213-113">Requirements</span></span>  
 <span data-ttu-id="d5213-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5213-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5213-115">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="d5213-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d5213-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5213-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5213-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5213-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5213-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5213-118">See also</span></span>

- [<span data-ttu-id="d5213-119">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5213-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
