---
description: 'Más información sobre: ICLRStrongName:: Gethashfromfile ((método)'
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
ms.openlocfilehash: e930f1c21e5b0be441fe44ad352b2ef2f43d0f67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637058"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="6fecc-103">ICLRStrongName::GetHashFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="6fecc-103">ICLRStrongName::GetHashFromFile Method</span></span>

<span data-ttu-id="6fecc-104">Genera un hash a partir del contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6fecc-104">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fecc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fecc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fecc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fecc-106">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="6fecc-107">de Nombre del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="6fecc-107">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="6fecc-108">[in, out] Algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="6fecc-108">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="6fecc-109">Los algoritmos válidos son los definidos por la CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="6fecc-109">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="6fecc-110">Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="6fecc-110">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="6fecc-111">enuncia Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="6fecc-111">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="6fecc-112">de Tamaño máximo del búfer `pbHash` al que apunta.</span><span class="sxs-lookup"><span data-stu-id="6fecc-112">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="6fecc-113">enuncia Tamaño, en bytes, del devuelto `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="6fecc-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fecc-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6fecc-114">Return Value</span></span>  

 <span data-ttu-id="6fecc-115">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="6fecc-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fecc-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6fecc-116">Remarks</span></span>  

 <span data-ttu-id="6fecc-117">Este método es el mismo que el método [ICLRStrongName:: GetHashFromFileW (](iclrstrongname-gethashfromfilew-method.md) , salvo que la especificación del nombre de archivo es ANSI en lugar de Unicode.</span><span class="sxs-lookup"><span data-stu-id="6fecc-117">This method is the same as the [ICLRStrongName::GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fecc-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fecc-118">Requirements</span></span>  

 <span data-ttu-id="6fecc-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fecc-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fecc-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="6fecc-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6fecc-121">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6fecc-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fecc-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fecc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fecc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fecc-123">See also</span></span>

- [<span data-ttu-id="6fecc-124">Método GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="6fecc-124">GetHashFromFileW Method</span></span>](iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="6fecc-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fecc-125">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
