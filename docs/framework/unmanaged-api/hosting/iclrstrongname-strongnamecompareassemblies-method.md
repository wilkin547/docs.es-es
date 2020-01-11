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
ms.openlocfilehash: 16b51393c945061efb0e94e48e5388c60472ee11
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899751"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="fbe41-102">ICLRStrongName::StrongNameCompareAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="fbe41-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="fbe41-103">Determina si dos ensamblados presentan diferencias solo mediante sus firmas de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="fbe41-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbe41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbe41-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbe41-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="fbe41-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="fbe41-106">de Ruta de acceso al primer ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbe41-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="fbe41-107">de Ruta de acceso al segundo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbe41-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="fbe41-108">enuncia Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fbe41-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="fbe41-109">`SN_CMP_DIFFERENT` (0): especifica que los ensamblados contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="fbe41-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="fbe41-110">`SN_CMP_IDENTICAL` (1): especifica que los ensamblados son exactamente iguales, incluidas sus firmas y suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="fbe41-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="fbe41-111">`SN_CMP_SIGONLY` (2): especifica que los ensamblados difieren solo en la firma y la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="fbe41-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbe41-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fbe41-112">Return Value</span></span>  
 <span data-ttu-id="fbe41-113">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="fbe41-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbe41-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="fbe41-114">Requirements</span></span>  
 <span data-ttu-id="fbe41-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbe41-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbe41-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="fbe41-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fbe41-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fbe41-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbe41-118">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbe41-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbe41-119">Notas</span><span class="sxs-lookup"><span data-stu-id="fbe41-119">Remarks</span></span>  
 <span data-ttu-id="fbe41-120">La firma de nombre seguro de un ensamblado consta del nombre de texto, la versión, la referencia cultural y el token de clave pública del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbe41-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe41-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbe41-121">See also</span></span>

- [<span data-ttu-id="fbe41-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbe41-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
