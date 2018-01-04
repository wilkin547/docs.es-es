---
title: "ICLRStrongName::StrongNameCompareAssemblies (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96fbeccf76de87a3582bf8c2084d0ca9ad7d27f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="ae2c0-102">ICLRStrongName::StrongNameCompareAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="ae2c0-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="ae2c0-103">Determina si dos ensamblados difieren solo en sus firmas de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="ae2c0-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae2c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae2c0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae2c0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae2c0-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="ae2c0-106">[in] La ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ae2c0-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="ae2c0-107">[in] La ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ae2c0-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="ae2c0-108">[out] Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ae2c0-108">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="ae2c0-109">`SN_CMP_DIFFERENT`(0): Especifica que los ensamblados contienen datos distintos.</span><span class="sxs-lookup"><span data-stu-id="ae2c0-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="ae2c0-110">`SN_CMP_IDENTICAL`(1): Especifica que los ensamblados son exactamente iguales, incluidas sus firmas y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="ae2c0-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="ae2c0-111">`SN_CMP_SIGONLY`(2): Especifica si los ensamblados difieren solo en la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="ae2c0-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae2c0-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae2c0-112">Return Value</span></span>  
 <span data-ttu-id="ae2c0-113">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="ae2c0-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae2c0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae2c0-114">Requirements</span></span>  
 <span data-ttu-id="ae2c0-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae2c0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae2c0-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ae2c0-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ae2c0-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae2c0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae2c0-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae2c0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae2c0-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae2c0-119">Remarks</span></span>  
 <span data-ttu-id="ae2c0-120">La firma de nombre seguro de un ensamblado consta del nombre de texto, versión, referencia cultural y token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ae2c0-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae2c0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae2c0-121">See Also</span></span>  
 [<span data-ttu-id="ae2c0-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae2c0-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
