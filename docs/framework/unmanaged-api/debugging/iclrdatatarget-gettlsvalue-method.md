---
title: ICLRDataTarget::GetTLSValue (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7de415b998ef97e7500c289a1bca4402d203b152
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738690"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="a783e-102">ICLRDataTarget::GetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="a783e-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="a783e-103">Obtiene un valor desde el almacenamiento local de subproceso (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="a783e-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="a783e-104">Este método llama a los servicios de acceso de datos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a783e-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a783e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a783e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a783e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a783e-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="a783e-107">[in] El identificador del sistema operativo de un subproceso del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="a783e-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="a783e-108">[in] El índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="a783e-108">[in] The index of the location.</span></span> <span data-ttu-id="a783e-109">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="a783e-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="a783e-110">[out] Un puntero a un `CLRDATA_ADDRESS` valor que especifica el valor devuelto desde la ubicación especificada de TLS.</span><span class="sxs-lookup"><span data-stu-id="a783e-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a783e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a783e-111">Remarks</span></span>  
 <span data-ttu-id="a783e-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="a783e-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a783e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a783e-113">Requirements</span></span>  
 <span data-ttu-id="a783e-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a783e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a783e-115">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="a783e-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a783e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a783e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a783e-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a783e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a783e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a783e-118">See also</span></span>

- [<span data-ttu-id="a783e-119">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a783e-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
