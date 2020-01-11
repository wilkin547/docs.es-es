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
ms.openlocfilehash: c095c99ee60d6b2ea0e5bce7010a66d40160443d
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899681"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="d9fab-102">ICLRStrongName::GetHashFromHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="d9fab-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="d9fab-103">Genera un hash sobre el contenido del archivo que tiene el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="d9fab-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9fab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9fab-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d9fab-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="d9fab-106">de Identificador del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d9fab-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d9fab-107">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d9fab-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d9fab-108">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d9fab-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d9fab-109">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="d9fab-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d9fab-110">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d9fab-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d9fab-111">enuncia Tamaño, en bytes, del `pbHash`devuelto.</span><span class="sxs-lookup"><span data-stu-id="d9fab-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9fab-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9fab-112">Return Value</span></span>  
 <span data-ttu-id="d9fab-113">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="d9fab-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9fab-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d9fab-114">Requirements</span></span>  
 <span data-ttu-id="d9fab-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9fab-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9fab-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d9fab-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d9fab-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d9fab-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9fab-118">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9fab-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fab-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9fab-119">See also</span></span>

- [<span data-ttu-id="d9fab-120">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9fab-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
