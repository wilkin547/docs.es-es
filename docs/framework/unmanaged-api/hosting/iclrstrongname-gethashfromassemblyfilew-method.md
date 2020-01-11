---
title: ICLRStrongName::GetHashFromAssemblyFileW (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: d98181e0d43206bfbf96182d7e4acf33da486348
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901172"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="624ef-102">ICLRStrongName::GetHashFromAssemblyFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="624ef-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="624ef-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="624ef-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="624ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="624ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="624ef-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="624ef-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="624ef-106">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="624ef-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="624ef-107">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="624ef-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="624ef-108">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="624ef-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="624ef-109">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="624ef-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="624ef-110">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="624ef-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="624ef-111">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="624ef-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="624ef-112">enuncia El tamaño devuelto, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="624ef-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="624ef-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="624ef-113">Return Value</span></span>  
 <span data-ttu-id="624ef-114">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="624ef-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="624ef-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="624ef-115">Requirements</span></span>  
 <span data-ttu-id="624ef-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="624ef-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="624ef-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="624ef-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="624ef-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="624ef-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="624ef-119">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="624ef-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="624ef-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="624ef-120">See also</span></span>

- [<span data-ttu-id="624ef-121">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="624ef-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="624ef-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="624ef-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
