---
title: ICLRStrongName::StrongNameCompareAssemblies (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eb23da5accd89931ee4b883bfa162035ec26ddd
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861041"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="98714-102">ICLRStrongName::StrongNameCompareAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="98714-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="98714-103">Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="98714-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98714-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98714-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98714-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98714-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="98714-106">[in] La ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98714-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="98714-107">[in] La ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98714-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="98714-108">[out] Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="98714-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="98714-109">`SN_CMP_DIFFERENT` (0): Especifica que los ensamblados contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="98714-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="98714-110">`SN_CMP_IDENTICAL` (1): Especifica que los ensamblados son exactamente las mismas, incluidos sus firmas y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="98714-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="98714-111">`SN_CMP_SIGONLY` (2): Especifica que los ensamblados se diferencian únicamente por la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="98714-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98714-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98714-112">Return Value</span></span>  
 <span data-ttu-id="98714-113">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="98714-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98714-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98714-114">Requirements</span></span>  
 <span data-ttu-id="98714-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98714-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98714-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="98714-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="98714-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98714-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98714-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98714-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98714-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98714-119">Remarks</span></span>  
 <span data-ttu-id="98714-120">La firma de nombre seguro de un ensamblado consta del nombre de texto, versión, referencia cultural y token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98714-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98714-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="98714-121">See Also</span></span>  
 [<span data-ttu-id="98714-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98714-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
