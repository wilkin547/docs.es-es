---
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
ms.openlocfilehash: adde52dddb63b83dcd7ff10703a43928d9601c92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140621"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="abbd7-102">StrongNameCompareAssemblies (Función)</span><span class="sxs-lookup"><span data-stu-id="abbd7-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="abbd7-103">Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="abbd7-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="abbd7-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="abbd7-104">This function has been deprecated.</span></span> <span data-ttu-id="abbd7-105">Use el método [ICLRStrongName:: StrongNameCompareAssemblies (](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="abbd7-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abbd7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abbd7-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abbd7-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abbd7-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="abbd7-108">de Ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="abbd7-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="abbd7-109">de Ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="abbd7-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="abbd7-110">enuncia Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="abbd7-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="abbd7-111">`SN_CMP_DIFFERENT` (0): especifica que los ensamblados contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="abbd7-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="abbd7-112">`SN_CMP_IDENTICAL` (1): especifica que los ensamblados son exactamente iguales, incluidas sus firmas y suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="abbd7-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="abbd7-113">`SN_CMP_SIGONLY` (2): especifica que los ensamblados difieren solo en la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="abbd7-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abbd7-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="abbd7-114">Return Value</span></span>  
 <span data-ttu-id="abbd7-115">`true` cuando se complete correctamente; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="abbd7-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abbd7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abbd7-116">Requirements</span></span>  
 <span data-ttu-id="abbd7-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abbd7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abbd7-118">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="abbd7-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="abbd7-119">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="abbd7-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="abbd7-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abbd7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abbd7-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abbd7-121">Remarks</span></span>  
 <span data-ttu-id="abbd7-122">La firma de nombre seguro de un ensamblado consta del nombre de texto, la versión, la referencia cultural y el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="abbd7-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="abbd7-123">Si la función `StrongNameCompareAssemblies` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="abbd7-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbd7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="abbd7-124">See also</span></span>

- [<span data-ttu-id="abbd7-125">StrongNameCompareAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="abbd7-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="abbd7-126">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abbd7-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
