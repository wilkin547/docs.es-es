---
title: "StrongNameCompareAssemblies (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameCompareAssemblies
helpviewer_keywords: StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3453cffb5e98e3623565785ab64db4f455be981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="83a4e-102">StrongNameCompareAssemblies (Función)</span><span class="sxs-lookup"><span data-stu-id="83a4e-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="83a4e-103">Determina si dos ensamblados difieren solo en sus firmas de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="83a4e-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="83a4e-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="83a4e-104">This function has been deprecated.</span></span> <span data-ttu-id="83a4e-105">Use la [ICLRStrongName:: StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="83a4e-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a4e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83a4e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83a4e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83a4e-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="83a4e-108">[in] La ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="83a4e-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="83a4e-109">[in] La ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="83a4e-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="83a4e-110">[out] Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="83a4e-110">[out] One of the following values:</span></span>  
  
-   <span data-ttu-id="83a4e-111">`SN_CMP_DIFFERENT`(0): Especifica que los ensamblados contienen datos distintos.</span><span class="sxs-lookup"><span data-stu-id="83a4e-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
-   <span data-ttu-id="83a4e-112">`SN_CMP_IDENTICAL`(1): Especifica que los ensamblados son exactamente iguales, incluidas sus firmas y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="83a4e-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   <span data-ttu-id="83a4e-113">`SN_CMP_SIGONLY`(2): Especifica si los ensamblados difieren solo en la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="83a4e-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83a4e-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="83a4e-114">Return Value</span></span>  
 <span data-ttu-id="83a4e-115">`true`Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="83a4e-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83a4e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83a4e-116">Requirements</span></span>  
 <span data-ttu-id="83a4e-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83a4e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83a4e-118">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="83a4e-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="83a4e-119">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83a4e-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83a4e-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83a4e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83a4e-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83a4e-121">Remarks</span></span>  
 <span data-ttu-id="83a4e-122">La firma de nombre seguro de un ensamblado consta del nombre de texto, versión, referencia cultural y token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="83a4e-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="83a4e-123">Si el `StrongNameCompareAssemblies` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="83a4e-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a4e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="83a4e-124">See Also</span></span>  
 [<span data-ttu-id="83a4e-125">StrongNameCompareAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="83a4e-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)  
 [<span data-ttu-id="83a4e-126">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83a4e-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
