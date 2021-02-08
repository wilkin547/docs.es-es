---
description: 'Más información sobre: ICorDebugRemoteTarget:: GetHostName ((método)'
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
ms.openlocfilehash: a24f34dd638c7031211c2185cd761af0aa24105e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803531"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="54dad-103">ICorDebugRemoteTarget::GetHostName (Método)</span><span class="sxs-lookup"><span data-stu-id="54dad-103">ICorDebugRemoteTarget::GetHostName Method</span></span>

<span data-ttu-id="54dad-104">Devuelve el nombre de dominio completo o la dirección IPv4 del equipo de destino de depuración remota.</span><span class="sxs-lookup"><span data-stu-id="54dad-104">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="54dad-105">IPV6 no se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="54dad-105">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54dad-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54dad-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="54dad-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54dad-107">Parameters</span></span>  

 `cchHostName`  
 <span data-ttu-id="54dad-108">[in] Tamaño, en caracteres, del búfer de `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="54dad-108">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="54dad-109">Si este parámetros es 0 (cero), `szHostName` debe ser NULL.</span><span class="sxs-lookup"><span data-stu-id="54dad-109">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="54dad-110">[out] Número de caracteres, incluido un terminador nulo, en el nombre de host o dirección IP.</span><span class="sxs-lookup"><span data-stu-id="54dad-110">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="54dad-111">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="54dad-111">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="54dad-112">[out] Búfer que contiene el nombre de host o la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="54dad-112">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54dad-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="54dad-113">Return Value</span></span>  

 <span data-ttu-id="54dad-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="54dad-114">S_OK</span></span>  
 <span data-ttu-id="54dad-115">El nombre de host o la dirección IP se devolvieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="54dad-115">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="54dad-116">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="54dad-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="54dad-117">No se puede devolver el nombre de host o la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="54dad-117">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54dad-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54dad-118">Remarks</span></span>  

 <span data-ttu-id="54dad-119">Este método lo implementa el programador del depurador.</span><span class="sxs-lookup"><span data-stu-id="54dad-119">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="54dad-120">Debe seguir el paradigma de llamada múltiple: en la primera llamada, el llamador pasa null a `cchHostName` y `szHostName` , y `pcchHostName` devuelve el tamaño del búfer necesario.</span><span class="sxs-lookup"><span data-stu-id="54dad-120">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="54dad-121">En la segunda llamada, el tamaño devuelto previamente se pasa en `cchHostName`, y un búfer del tamaño adecuado se pasa en `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="54dad-121">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54dad-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54dad-122">Requirements</span></span>  

 <span data-ttu-id="54dad-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54dad-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54dad-124">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="54dad-124">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="54dad-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54dad-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54dad-126">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="54dad-126">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54dad-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="54dad-127">See also</span></span>

- [<span data-ttu-id="54dad-128">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="54dad-128">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="54dad-129">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="54dad-129">ICorDebug Interface</span></span>](icordebug-interface.md)
