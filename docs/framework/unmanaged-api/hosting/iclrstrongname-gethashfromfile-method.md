---
title: ICLRStrongName::GetHashFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: 9561d383e7c134230b8664329b59aec23e487124
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899577"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="a0bb2-102">ICLRStrongName::GetHashFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="a0bb2-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="a0bb2-103">Genera un hash a partir del contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0bb2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0bb2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0bb2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a0bb2-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="a0bb2-106">de Nombre del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a0bb2-107">[in, out] Algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="a0bb2-108">Los algoritmos válidos son los definidos por la CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="a0bb2-109">Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a0bb2-110">enuncia Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a0bb2-111">de Tamaño máximo del búfer al que apunta `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a0bb2-112">enuncia Tamaño, en bytes, del `pbHash`devuelto.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0bb2-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a0bb2-113">Return Value</span></span>  
 <span data-ttu-id="a0bb2-114">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="a0bb2-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0bb2-115">Notas</span><span class="sxs-lookup"><span data-stu-id="a0bb2-115">Remarks</span></span>  
 <span data-ttu-id="a0bb2-116">Este método es el mismo que el método [ICLRStrongName:: GetHashFromFileW (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) , salvo que la especificación del nombre de archivo es ANSI en lugar de Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0bb2-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0bb2-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a0bb2-117">Requirements</span></span>  
 <span data-ttu-id="a0bb2-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0bb2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0bb2-119">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a0bb2-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a0bb2-120">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a0bb2-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0bb2-121">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0bb2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bb2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0bb2-122">See also</span></span>

- [<span data-ttu-id="a0bb2-123">GetHashFromFileW (método)</span><span class="sxs-lookup"><span data-stu-id="a0bb2-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="a0bb2-124">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0bb2-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
