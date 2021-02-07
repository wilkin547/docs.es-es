---
description: 'Más información acerca de: StrongNameCompareAssemblies ((función)'
title: StrongNameCompareAssemblies (Función)
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
ms.openlocfilehash: e59bb96a89dc1e1cf8b809c3e0d538aaffe83b8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736567"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="bc2d7-103">StrongNameCompareAssemblies (Función)</span><span class="sxs-lookup"><span data-stu-id="bc2d7-103">StrongNameCompareAssemblies Function</span></span>

<span data-ttu-id="bc2d7-104">Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-104">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="bc2d7-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-105">This function has been deprecated.</span></span> <span data-ttu-id="bc2d7-106">Use el método [ICLRStrongName:: StrongNameCompareAssemblies (](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-106">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc2d7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc2d7-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc2d7-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc2d7-108">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="bc2d7-109">de Ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-109">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="bc2d7-110">de Ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-110">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="bc2d7-111">enuncia Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="bc2d7-111">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="bc2d7-112">`SN_CMP_DIFFERENT` (0): especifica que los ensamblados contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-112">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="bc2d7-113">`SN_CMP_IDENTICAL` (1): especifica que los ensamblados son exactamente iguales, incluidas sus firmas y suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-113">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="bc2d7-114">`SN_CMP_SIGONLY` (2): especifica que los ensamblados solo se diferencian en la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-114">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc2d7-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bc2d7-115">Return Value</span></span>  

 <span data-ttu-id="bc2d7-116">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="bc2d7-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc2d7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc2d7-117">Requirements</span></span>  

 <span data-ttu-id="bc2d7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc2d7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc2d7-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="bc2d7-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bc2d7-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc2d7-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc2d7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc2d7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc2d7-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc2d7-122">Remarks</span></span>  

 <span data-ttu-id="bc2d7-123">La firma de nombre seguro de un ensamblado consta del nombre de texto, la versión, la referencia cultural y el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-123">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="bc2d7-124">Si la `StrongNameCompareAssemblies` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-124">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2d7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc2d7-125">See also</span></span>

- [<span data-ttu-id="bc2d7-126">Método StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="bc2d7-126">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="bc2d7-127">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc2d7-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
