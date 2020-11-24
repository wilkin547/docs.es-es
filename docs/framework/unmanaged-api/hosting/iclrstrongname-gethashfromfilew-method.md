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
ms.openlocfilehash: eda78976f175230cc2405b9cb151993e63697e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685765"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="3c161-102">ICLRStrongName::GetHashFromFileW (Método)</span><span class="sxs-lookup"><span data-stu-id="3c161-102">ICLRStrongName::GetHashFromFileW Method</span></span>

<span data-ttu-id="3c161-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="3c161-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c161-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c161-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="3c161-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c161-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="3c161-106">de Nombre Unicode del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="3c161-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="3c161-107">[in, out] Algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="3c161-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="3c161-108">Los algoritmos válidos son los definidos por la CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="3c161-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="3c161-109">Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="3c161-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="3c161-110">enuncia Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="3c161-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="3c161-111">de Tamaño máximo del búfer al que apunta `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="3c161-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="3c161-112">enuncia Tamaño, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="3c161-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c161-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c161-113">Return Value</span></span>  

 <span data-ttu-id="3c161-114">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="3c161-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c161-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c161-115">Remarks</span></span>  

 <span data-ttu-id="3c161-116">Este método es el mismo que el método [ICLRStrongName:: gethashfromfile (](iclrstrongname-gethashfromfile-method.md) , salvo que la especificación del nombre de archivo es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="3c161-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c161-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c161-117">Requirements</span></span>  

 <span data-ttu-id="3c161-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c161-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c161-119">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="3c161-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3c161-120">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c161-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c161-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c161-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c161-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c161-122">See also</span></span>

- [<span data-ttu-id="3c161-123">Método GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="3c161-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="3c161-124">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c161-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
