---
title: ICLRStrongName::GetHashFromFileW (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176375"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="a5b39-102">ICLRStrongName::GetHashFromFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="a5b39-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="a5b39-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="a5b39-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5b39-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="a5b39-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5b39-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a5b39-106">[en] El nombre Unicode del archivo que se ha hash.</span><span class="sxs-lookup"><span data-stu-id="a5b39-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a5b39-107">[adentro, fuera] El algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="a5b39-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="a5b39-108">Los algoritmos válidos son los definidos por Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="a5b39-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="a5b39-109">Si `piHashAlg` se establece en 0, se utiliza el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="a5b39-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a5b39-110">[fuera] Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="a5b39-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a5b39-111">[en] El tamaño máximo del búfer `pbHash`al que apunta .</span><span class="sxs-lookup"><span data-stu-id="a5b39-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a5b39-112">[fuera] El tamaño, en `pbHash`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="a5b39-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5b39-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5b39-113">Return Value</span></span>  
 <span data-ttu-id="a5b39-114">`S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="a5b39-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5b39-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5b39-115">Remarks</span></span>  
 <span data-ttu-id="a5b39-116">Este método es el mismo que el [método ICLRStrongName::GetHashFromFile,](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) excepto que la especificación de nombre de archivo es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="a5b39-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b39-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5b39-117">Requirements</span></span>  
 <span data-ttu-id="a5b39-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5b39-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5b39-119">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a5b39-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a5b39-120">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5b39-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5b39-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5b39-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b39-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5b39-122">See also</span></span>

- [<span data-ttu-id="a5b39-123">Método GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="a5b39-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="a5b39-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5b39-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
