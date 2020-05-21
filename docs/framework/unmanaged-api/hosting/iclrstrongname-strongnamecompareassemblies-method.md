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
ms.openlocfilehash: 0087636c68d0748ad2b143de9b132278ab9d43f5
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762063"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="76214-102">ICLRStrongName::StrongNameCompareAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="76214-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="76214-103">Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="76214-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76214-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76214-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76214-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76214-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="76214-106">de Ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="76214-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="76214-107">de Ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="76214-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="76214-108">enuncia Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="76214-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="76214-109">`SN_CMP_DIFFERENT`(0): especifica que los ensamblados contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="76214-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="76214-110">`SN_CMP_IDENTICAL`(1): especifica que los ensamblados son exactamente iguales, incluidas sus firmas y suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="76214-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="76214-111">`SN_CMP_SIGONLY`(2): especifica que los ensamblados solo se diferencian en la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="76214-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76214-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76214-112">Return Value</span></span>  
 <span data-ttu-id="76214-113">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="76214-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76214-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76214-114">Requirements</span></span>  
 <span data-ttu-id="76214-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76214-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76214-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="76214-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="76214-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76214-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76214-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76214-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76214-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76214-119">Remarks</span></span>  
 <span data-ttu-id="76214-120">La firma de nombre seguro de un ensamblado consta del nombre de texto, la versión, la referencia cultural y el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="76214-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76214-121">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="76214-121">See also</span></span>

- [<span data-ttu-id="76214-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76214-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
