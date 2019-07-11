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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a5b5eb587a4739cf3481c76ef73ebc62f0a9d20
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748171"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="fe66a-102">ICLRStrongName::GetHashFromFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="fe66a-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="fe66a-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="fe66a-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe66a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe66a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="fe66a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe66a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="fe66a-106">[in] Nombre del archivo al hash de Unicode.</span><span class="sxs-lookup"><span data-stu-id="fe66a-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fe66a-107">[in, out] El algoritmo que se utilizará al generar el código hash.</span><span class="sxs-lookup"><span data-stu-id="fe66a-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="fe66a-108">Los algoritmos válidos son los definidos por CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="fe66a-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="fe66a-109">Si `piHashAlg` se establece en 0, el algoritmo predeterminado CALG_SHA-1 se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fe66a-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fe66a-110">[out] Una matriz de bytes que contiene el código hash generado.</span><span class="sxs-lookup"><span data-stu-id="fe66a-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fe66a-111">[in] El tamaño máximo del búfer señalado por `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="fe66a-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fe66a-112">[out] El tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="fe66a-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe66a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fe66a-113">Return Value</span></span>  
 <span data-ttu-id="fe66a-114">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="fe66a-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe66a-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe66a-115">Remarks</span></span>  
 <span data-ttu-id="fe66a-116">Este método es el mismo que el [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) método, salvo que el nombre del archivo especificación es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="fe66a-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe66a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe66a-117">Requirements</span></span>  
 <span data-ttu-id="fe66a-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe66a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe66a-119">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fe66a-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fe66a-120">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe66a-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe66a-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe66a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe66a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe66a-122">See also</span></span>

- [<span data-ttu-id="fe66a-123">GetHashFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="fe66a-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="fe66a-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe66a-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
