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
ms.openlocfilehash: 43a5cd57a8eeaba70f1bb1ffb9cab5bb1a067914
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130949"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="d52f3-102">ICLRStrongName::GetHashFromAssemblyFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="d52f3-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="d52f3-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="d52f3-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d52f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d52f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d52f3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d52f3-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d52f3-106">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d52f3-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="d52f3-107">Este parámetro debe ser una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="d52f3-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d52f3-108">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d52f3-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d52f3-109">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d52f3-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d52f3-110">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="d52f3-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d52f3-111">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d52f3-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d52f3-112">enuncia El tamaño devuelto, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d52f3-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d52f3-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d52f3-113">Return Value</span></span>  
 <span data-ttu-id="d52f3-114">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).</span><span class="sxs-lookup"><span data-stu-id="d52f3-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d52f3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d52f3-115">Requirements</span></span>  
 <span data-ttu-id="d52f3-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d52f3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52f3-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d52f3-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d52f3-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d52f3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d52f3-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d52f3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52f3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d52f3-120">See also</span></span>

- [<span data-ttu-id="d52f3-121">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="d52f3-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="d52f3-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d52f3-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
