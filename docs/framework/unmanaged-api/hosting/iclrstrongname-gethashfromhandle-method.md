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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20c5f6bbb58b85f42ec00e356eccc5fb41ce813c
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46481207"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="567bb-102">ICLRStrongName::GetHashFromHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="567bb-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="567bb-103">Genera un hash del contenido del archivo que tiene el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="567bb-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="567bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="567bb-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="567bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="567bb-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="567bb-106">[in] El identificador del archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="567bb-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="567bb-107">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="567bb-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="567bb-108">Usar cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="567bb-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="567bb-109">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="567bb-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="567bb-110">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="567bb-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="567bb-111">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="567bb-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="567bb-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="567bb-112">Return Value</span></span>  
 <span data-ttu-id="567bb-113">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="567bb-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="567bb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="567bb-114">Requirements</span></span>  
 <span data-ttu-id="567bb-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="567bb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="567bb-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="567bb-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="567bb-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="567bb-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="567bb-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="567bb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="567bb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="567bb-119">See Also</span></span>  
 [<span data-ttu-id="567bb-120">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="567bb-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
