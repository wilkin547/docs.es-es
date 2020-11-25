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
ms.openlocfilehash: 6b67aed90585f57d2635bb1a22d3e009edf01159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714814"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="80d13-102">ICLRStrongName::GetHashFromBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="80d13-102">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="80d13-103">Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="80d13-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80d13-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="80d13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80d13-105">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="80d13-106">de Puntero a la dirección del bloque de memoria al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="80d13-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="80d13-107">de La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="80d13-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="80d13-108">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="80d13-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="80d13-109">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="80d13-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="80d13-110">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="80d13-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="80d13-111">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="80d13-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="80d13-112">enuncia Tamaño, en bytes, del devuelto `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="80d13-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80d13-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80d13-113">Return Value</span></span>  

 <span data-ttu-id="80d13-114">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="80d13-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80d13-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80d13-115">Requirements</span></span>  

 <span data-ttu-id="80d13-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80d13-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80d13-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="80d13-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="80d13-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80d13-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80d13-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80d13-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d13-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80d13-120">See also</span></span>

- [<span data-ttu-id="80d13-121">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80d13-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
