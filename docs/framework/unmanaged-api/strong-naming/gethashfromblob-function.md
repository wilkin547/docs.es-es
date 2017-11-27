---
title: "GetHashFromBlob (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromBlob
helpviewer_keywords: GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 360036cd1578c2845f09f92c09d79e44618abe75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="1ba18-102">GetHashFromBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="1ba18-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="1ba18-103">Obtiene un valor hash del ensamblado en la dirección de memoria especificada, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="1ba18-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="1ba18-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="1ba18-104">This function has been deprecated.</span></span> <span data-ttu-id="1ba18-105">Use la [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1ba18-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba18-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ba18-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ba18-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ba18-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="1ba18-108">[in] Un puntero a la dirección del bloque de memoria para realizar el hash.</span><span class="sxs-lookup"><span data-stu-id="1ba18-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="1ba18-109">[in] La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="1ba18-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1ba18-110">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="1ba18-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1ba18-111">Utilice un cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1ba18-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1ba18-112">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="1ba18-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1ba18-113">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1ba18-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1ba18-114">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1ba18-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba18-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ba18-115">Requirements</span></span>  
 <span data-ttu-id="1ba18-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ba18-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba18-117">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1ba18-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1ba18-118">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ba18-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ba18-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba18-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba18-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ba18-120">See Also</span></span>  
 [<span data-ttu-id="1ba18-121">GetHashFromBlob (método)</span><span class="sxs-lookup"><span data-stu-id="1ba18-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="1ba18-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ba18-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
