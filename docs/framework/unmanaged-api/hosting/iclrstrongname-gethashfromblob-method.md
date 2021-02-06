---
description: 'Más información sobre: ICLRStrongName:: GetHashFromBlob ((método)'
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
ms.openlocfilehash: 20d03184f57e77741e656575038e426ee37968f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637071"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="b4dc0-103">ICLRStrongName::GetHashFromBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="b4dc0-103">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="b4dc0-104">Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="b4dc0-104">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4dc0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4dc0-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b4dc0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4dc0-106">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="b4dc0-107">de Puntero a la dirección del bloque de memoria al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="b4dc0-107">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="b4dc0-108">de La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="b4dc0-108">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="b4dc0-109">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="b4dc0-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="b4dc0-110">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b4dc0-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="b4dc0-111">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="b4dc0-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="b4dc0-112">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="b4dc0-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="b4dc0-113">enuncia Tamaño, en bytes, del devuelto `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="b4dc0-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4dc0-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4dc0-114">Return Value</span></span>  

 <span data-ttu-id="b4dc0-115">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="b4dc0-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4dc0-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4dc0-116">Requirements</span></span>  

 <span data-ttu-id="b4dc0-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4dc0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4dc0-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="b4dc0-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b4dc0-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4dc0-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4dc0-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4dc0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4dc0-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4dc0-121">See also</span></span>

- [<span data-ttu-id="b4dc0-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4dc0-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
