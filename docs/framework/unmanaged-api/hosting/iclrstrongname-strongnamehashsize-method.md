---
title: ICLRStrongName::StrongNameHashSize (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: 0f4fdcbdfb9db7664920a42b9406a58f9c2de0b8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763116"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="7972e-102">ICLRStrongName::StrongNameHashSize (Método)</span><span class="sxs-lookup"><span data-stu-id="7972e-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="7972e-103">Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="7972e-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7972e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7972e-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7972e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7972e-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="7972e-106">de Algoritmo hash que se usa para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="7972e-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7972e-107">enuncia Tamaño de búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="7972e-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7972e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7972e-108">Return Value</span></span>  
 <span data-ttu-id="7972e-109">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="7972e-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7972e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7972e-110">Requirements</span></span>  
 <span data-ttu-id="7972e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7972e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7972e-112">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="7972e-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7972e-113">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7972e-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7972e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7972e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7972e-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7972e-115">See also</span></span>

- [<span data-ttu-id="7972e-116">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7972e-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
