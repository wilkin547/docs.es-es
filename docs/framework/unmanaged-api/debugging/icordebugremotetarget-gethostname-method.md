---
title: ICorDebugRemoteTarget::GetHostName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf35715564e58f1811618b6859a860008e9660c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655405"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="77c4a-102">ICorDebugRemoteTarget::GetHostName (Método)</span><span class="sxs-lookup"><span data-stu-id="77c4a-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="77c4a-103">Devuelve el nombre de dominio completo o la dirección IPv4 del equipo de destino de depuración remota.</span><span class="sxs-lookup"><span data-stu-id="77c4a-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="77c4a-104">IPV6 no se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="77c4a-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77c4a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77c4a-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77c4a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77c4a-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="77c4a-107">[in] Tamaño, en caracteres, del búfer de `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="77c4a-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="77c4a-108">Si este parámetros es 0 (cero), `szHostName` debe ser NULL.</span><span class="sxs-lookup"><span data-stu-id="77c4a-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="77c4a-109">[out] Número de caracteres, incluido un terminador nulo, en el nombre de host o dirección IP.</span><span class="sxs-lookup"><span data-stu-id="77c4a-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="77c4a-110">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="77c4a-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="77c4a-111">[out] Búfer que contiene el nombre de host o la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="77c4a-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77c4a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="77c4a-112">Return Value</span></span>  
 <span data-ttu-id="77c4a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="77c4a-113">S_OK</span></span>  
 <span data-ttu-id="77c4a-114">El nombre de host o la dirección IP se devolvieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="77c4a-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="77c4a-115">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="77c4a-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="77c4a-116">No se puede devolver el nombre de host o la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="77c4a-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77c4a-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77c4a-117">Remarks</span></span>  
 <span data-ttu-id="77c4a-118">Este método lo implementa el programador del depurador.</span><span class="sxs-lookup"><span data-stu-id="77c4a-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="77c4a-119">Debe seguir el paradigma de varias llamadas: En la primera llamada, el llamador pasa null a `cchHostName` y `szHostName`, y `pcchHostName` devuelve el tamaño del búfer necesario.</span><span class="sxs-lookup"><span data-stu-id="77c4a-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer .</span></span> <span data-ttu-id="77c4a-120">En la segunda llamada, el tamaño devuelto previamente se pasa en `cchHostName`, y un búfer del tamaño adecuado se pasa en `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="77c4a-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77c4a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77c4a-121">Requirements</span></span>  
 <span data-ttu-id="77c4a-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77c4a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77c4a-123">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="77c4a-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="77c4a-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77c4a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77c4a-125">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="77c4a-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c4a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="77c4a-126">See also</span></span>
- [<span data-ttu-id="77c4a-127">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="77c4a-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="77c4a-128">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="77c4a-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
