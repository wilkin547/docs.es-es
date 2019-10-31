---
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
ms.openlocfilehash: 19d4518b7ec125df717b2f901bbd92cbd1b659bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135161"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="76ce4-102">ICLRStrongName::GetHashFromHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="76ce4-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="76ce4-103">Genera un hash sobre el contenido del archivo que tiene el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="76ce4-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ce4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76ce4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ce4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76ce4-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="76ce4-106">de Identificador del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="76ce4-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="76ce4-107">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="76ce4-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="76ce4-108">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="76ce4-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="76ce4-109">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="76ce4-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="76ce4-110">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="76ce4-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="76ce4-111">enuncia Tamaño, en bytes, del `pbHash`devuelto.</span><span class="sxs-lookup"><span data-stu-id="76ce4-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76ce4-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76ce4-112">Return Value</span></span>  
 <span data-ttu-id="76ce4-113">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).</span><span class="sxs-lookup"><span data-stu-id="76ce4-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ce4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76ce4-114">Requirements</span></span>  
 <span data-ttu-id="76ce4-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ce4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ce4-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="76ce4-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="76ce4-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76ce4-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76ce4-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ce4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ce4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="76ce4-119">See also</span></span>

- [<span data-ttu-id="76ce4-120">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76ce4-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
