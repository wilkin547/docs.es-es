---
title: ICLRStrongName::GetHashFromBlob (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f84d50579feade09df1b42a8e2f0c6b3e6a94fac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771662"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="7ca20-102">ICLRStrongName::GetHashFromBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="7ca20-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="7ca20-103">Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="7ca20-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ca20-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7ca20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ca20-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="7ca20-106">[in] Un puntero a la dirección del bloque de memoria para un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="7ca20-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="7ca20-107">[in] La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="7ca20-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7ca20-108">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="7ca20-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="7ca20-109">Usar cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7ca20-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7ca20-110">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="7ca20-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7ca20-111">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7ca20-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7ca20-112">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7ca20-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ca20-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7ca20-113">Return Value</span></span>  
 <span data-ttu-id="7ca20-114">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="7ca20-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca20-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ca20-115">Requirements</span></span>  
 <span data-ttu-id="7ca20-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ca20-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca20-117">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7ca20-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7ca20-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ca20-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ca20-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca20-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca20-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ca20-120">See also</span></span>

- [<span data-ttu-id="7ca20-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ca20-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
