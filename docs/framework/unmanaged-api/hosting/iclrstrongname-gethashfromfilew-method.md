---
description: 'Más información sobre: ICLRStrongName:: GetHashFromFileW ((método)'
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
ms.openlocfilehash: 6145a044f490ef3827de6db8d84d16222306642d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636980"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="fa835-103">ICLRStrongName::GetHashFromFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="fa835-103">ICLRStrongName::GetHashFromFileW Method</span></span>

<span data-ttu-id="fa835-104">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="fa835-104">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa835-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa835-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="fa835-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa835-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="fa835-107">de Nombre Unicode del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="fa835-107">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fa835-108">[in, out] Algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="fa835-108">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="fa835-109">Los algoritmos válidos son los definidos por la CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="fa835-109">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="fa835-110">Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="fa835-110">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fa835-111">enuncia Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="fa835-111">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fa835-112">de Tamaño máximo del búfer al que apunta `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="fa835-112">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fa835-113">enuncia Tamaño, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="fa835-113">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa835-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa835-114">Return Value</span></span>  

 <span data-ttu-id="fa835-115">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="fa835-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa835-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa835-116">Remarks</span></span>  

 <span data-ttu-id="fa835-117">Este método es el mismo que el método [ICLRStrongName:: gethashfromfile (](iclrstrongname-gethashfromfile-method.md) , salvo que la especificación del nombre de archivo es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="fa835-117">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa835-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa835-118">Requirements</span></span>  

 <span data-ttu-id="fa835-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa835-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa835-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="fa835-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fa835-121">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa835-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa835-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa835-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa835-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa835-123">See also</span></span>

- [<span data-ttu-id="fa835-124">Método GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="fa835-124">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="fa835-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa835-125">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
