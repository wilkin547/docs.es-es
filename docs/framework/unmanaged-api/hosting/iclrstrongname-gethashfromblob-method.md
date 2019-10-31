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
ms.openlocfilehash: 0c9adcc252fe16c95da8b2afca45bb2ee5dc545a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135204"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="f3cbf-102">ICLRStrongName::GetHashFromBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="f3cbf-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="f3cbf-103">Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3cbf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3cbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3cbf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3cbf-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="f3cbf-106">de Puntero a la dirección del bloque de memoria al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="f3cbf-107">de La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f3cbf-108">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f3cbf-109">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f3cbf-110">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f3cbf-111">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f3cbf-112">enuncia Tamaño, en bytes, del `pbHash`devuelto.</span><span class="sxs-lookup"><span data-stu-id="f3cbf-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3cbf-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f3cbf-113">Return Value</span></span>  
 <span data-ttu-id="f3cbf-114">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).</span><span class="sxs-lookup"><span data-stu-id="f3cbf-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3cbf-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3cbf-115">Requirements</span></span>  
 <span data-ttu-id="f3cbf-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3cbf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3cbf-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f3cbf-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f3cbf-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3cbf-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3cbf-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3cbf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3cbf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3cbf-120">See also</span></span>

- [<span data-ttu-id="f3cbf-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3cbf-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
