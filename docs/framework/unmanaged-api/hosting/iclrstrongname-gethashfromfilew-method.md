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
ms.openlocfilehash: acfa5c138faa47c96600530ab923de102b173ed6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672739"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="fdd82-102">ICLRStrongName::GetHashFromFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="fdd82-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="fdd82-103">Genera un hash del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="fdd82-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdd82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdd82-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdd82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdd82-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="fdd82-106">[in] Nombre del archivo al hash de Unicode.</span><span class="sxs-lookup"><span data-stu-id="fdd82-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fdd82-107">[in, out] El algoritmo que se utilizará al generar el código hash.</span><span class="sxs-lookup"><span data-stu-id="fdd82-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="fdd82-108">Los algoritmos válidos son los definidos por CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="fdd82-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="fdd82-109">Si `piHashAlg` se establece en 0, el algoritmo predeterminado CALG_SHA-1 se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fdd82-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fdd82-110">[out] Una matriz de bytes que contiene el código hash generado.</span><span class="sxs-lookup"><span data-stu-id="fdd82-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fdd82-111">[in] El tamaño máximo del búfer señalado por `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="fdd82-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fdd82-112">[out] El tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="fdd82-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdd82-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fdd82-113">Return Value</span></span>  
 <span data-ttu-id="fdd82-114">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="fdd82-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdd82-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdd82-115">Remarks</span></span>  
 <span data-ttu-id="fdd82-116">Este método es el mismo que el [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) método, salvo que el nombre del archivo especificación es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="fdd82-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdd82-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdd82-117">Requirements</span></span>  
 <span data-ttu-id="fdd82-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdd82-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdd82-119">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fdd82-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fdd82-120">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fdd82-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdd82-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdd82-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd82-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdd82-122">See Also</span></span>  
 [<span data-ttu-id="fdd82-123">GetHashFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="fdd82-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="fdd82-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdd82-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
