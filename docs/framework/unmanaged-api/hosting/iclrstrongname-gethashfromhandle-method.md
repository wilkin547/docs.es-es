---
description: 'Más información sobre: ICLRStrongName:: Gethashfromhandle ((método)'
title: ICLRStrongName::GetHashFromHandle (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
ms.openlocfilehash: 30248b5cb5d102adaa06293c92cc4f21e905cba5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799686"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="4ce45-103">ICLRStrongName::GetHashFromHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="4ce45-103">ICLRStrongName::GetHashFromHandle Method</span></span>

<span data-ttu-id="4ce45-104">Genera un hash sobre el contenido del archivo que tiene el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="4ce45-104">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ce45-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ce45-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ce45-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ce45-106">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="4ce45-107">de Identificador del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="4ce45-107">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="4ce45-108">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="4ce45-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="4ce45-109">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4ce45-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="4ce45-110">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="4ce45-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="4ce45-111">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="4ce45-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="4ce45-112">enuncia Tamaño, en bytes, del devuelto `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="4ce45-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ce45-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4ce45-113">Return Value</span></span>  

 <span data-ttu-id="4ce45-114">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="4ce45-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ce45-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ce45-115">Requirements</span></span>  

 <span data-ttu-id="4ce45-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ce45-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ce45-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4ce45-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4ce45-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ce45-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ce45-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ce45-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce45-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ce45-120">See also</span></span>

- [<span data-ttu-id="4ce45-121">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ce45-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
