---
description: 'Más información acerca de: ICLRDataTarget:: GetCurrentThreadID (método)'
title: ICLRDataTarget::GetCurrentThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
ms.openlocfilehash: ae1ef00fd6afbecf741d1e4ed215c816dcf6af8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801363"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="6dd26-103">ICLRDataTarget::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="6dd26-103">ICLRDataTarget::GetCurrentThreadID Method</span></span>

<span data-ttu-id="6dd26-104">Obtiene el identificador del sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="6dd26-104">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dd26-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6dd26-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dd26-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6dd26-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="6dd26-107">enuncia Puntero al identificador del sistema operativo del subproceso actual para el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="6dd26-107">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dd26-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6dd26-108">Remarks</span></span>  

 <span data-ttu-id="6dd26-109">Si no hay ningún subproceso actual para el proceso de destino, se `GetCurrentThreadID` puede producir un error en el método.</span><span class="sxs-lookup"><span data-stu-id="6dd26-109">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dd26-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dd26-110">Requirements</span></span>  

 <span data-ttu-id="6dd26-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dd26-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dd26-112">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="6dd26-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6dd26-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dd26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dd26-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dd26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd26-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dd26-115">See also</span></span>

- [<span data-ttu-id="6dd26-116">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dd26-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
