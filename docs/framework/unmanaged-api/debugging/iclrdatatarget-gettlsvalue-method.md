---
title: "ICLRDataTarget::GetTLSValue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetTLSValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a820ec7c0a00306266be432a8aceacb3d30d1b4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="d643f-102">ICLRDataTarget::GetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="d643f-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="d643f-103">Obtiene un valor desde el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d643f-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="d643f-104">Los servicios de acceso a datos de common language runtime (CLR) llama a este método.</span><span class="sxs-lookup"><span data-stu-id="d643f-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d643f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d643f-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d643f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d643f-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d643f-107">[in] El identificador de sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d643f-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="d643f-108">[in] El índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="d643f-108">[in] The index of the location.</span></span> <span data-ttu-id="d643f-109">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="d643f-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="d643f-110">[out] Un puntero a un `CLRDATA_ADDRESS` valor que especifica el valor devuelto desde la ubicación de TLS dada.</span><span class="sxs-lookup"><span data-stu-id="d643f-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d643f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d643f-111">Remarks</span></span>  
 <span data-ttu-id="d643f-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="d643f-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d643f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d643f-113">Requirements</span></span>  
 <span data-ttu-id="d643f-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d643f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d643f-115">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d643f-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d643f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d643f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d643f-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d643f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d643f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d643f-118">See Also</span></span>  
 [<span data-ttu-id="d643f-119">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d643f-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
