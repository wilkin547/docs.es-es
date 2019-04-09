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
ms.openlocfilehash: 6d11c71498053844792cd902959dee642877c46b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146983"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="fbf5a-102">ICLRStrongName::GetHashFromHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="fbf5a-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="fbf5a-103">Genera un hash del contenido del archivo que tiene el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="fbf5a-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbf5a-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbf5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fbf5a-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="fbf5a-106">[in] El identificador del archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="fbf5a-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fbf5a-107">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="fbf5a-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="fbf5a-108">Usar cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fbf5a-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fbf5a-109">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="fbf5a-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fbf5a-110">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="fbf5a-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fbf5a-111">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="fbf5a-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbf5a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fbf5a-112">Return Value</span></span>  
 `S_OK` <span data-ttu-id="fbf5a-113">Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="fbf5a-113">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbf5a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbf5a-114">Requirements</span></span>  
 <span data-ttu-id="fbf5a-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbf5a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf5a-116">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fbf5a-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fbf5a-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fbf5a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fbf5a-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fbf5a-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fbf5a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbf5a-119">See also</span></span>

- [<span data-ttu-id="fbf5a-120">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbf5a-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
