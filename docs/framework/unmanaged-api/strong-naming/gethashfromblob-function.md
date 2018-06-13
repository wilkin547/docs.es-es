---
title: GetHashFromBlob (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 427d93a9aff527d36720c4199782fa104a66f8d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455038"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="3d3f5-102">GetHashFromBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="3d3f5-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="3d3f5-103">Obtiene un valor hash del ensamblado en la dirección de memoria especificada, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="3d3f5-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-104">This function has been deprecated.</span></span> <span data-ttu-id="3d3f5-105">Use la [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d3f5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d3f5-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3d3f5-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d3f5-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="3d3f5-108">[in] Un puntero a la dirección del bloque de memoria para realizar el hash.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="3d3f5-109">[in] La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="3d3f5-110">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="3d3f5-111">Utilice un cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="3d3f5-112">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="3d3f5-113">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="3d3f5-114">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="3d3f5-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d3f5-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d3f5-115">Requirements</span></span>  
 <span data-ttu-id="3d3f5-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d3f5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d3f5-117">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="3d3f5-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3d3f5-118">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d3f5-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d3f5-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d3f5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d3f5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d3f5-120">See Also</span></span>  
 [<span data-ttu-id="3d3f5-121">GetHashFromBlob (método)</span><span class="sxs-lookup"><span data-stu-id="3d3f5-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="3d3f5-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d3f5-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
