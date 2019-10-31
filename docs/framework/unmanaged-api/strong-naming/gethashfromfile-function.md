---
title: GetHashFromFile (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ffa25b1ec6fda80099f333c1d0a4cf57b76379e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140694"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="7c51d-102">GetHashFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="7c51d-102">GetHashFromFile Function</span></span>
<span data-ttu-id="7c51d-103">Genera un hash a partir del contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="7c51d-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="7c51d-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="7c51d-104">This function has been deprecated.</span></span> <span data-ttu-id="7c51d-105">Use el método [ICLRStrongName:: gethashfromfile (](../hosting/iclrstrongname-gethashfromfile-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7c51d-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c51d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c51d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c51d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c51d-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="7c51d-108">de Nombre del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="7c51d-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7c51d-109">[in, out] Algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="7c51d-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="7c51d-110">Los algoritmos válidos son los definidos por la CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="7c51d-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="7c51d-111">Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="7c51d-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7c51d-112">enuncia Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="7c51d-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7c51d-113">de Tamaño máximo del búfer al que apunta `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7c51d-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7c51d-114">enuncia Tamaño, en bytes, del `pbHash`devuelto.</span><span class="sxs-lookup"><span data-stu-id="7c51d-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c51d-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c51d-115">Remarks</span></span>  
 <span data-ttu-id="7c51d-116">Esta función es igual que [GetHashFromFileW (](gethashfromfilew-function.md), salvo que la especificación de nombre de archivo es ANSI en lugar de Unicode.</span><span class="sxs-lookup"><span data-stu-id="7c51d-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c51d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c51d-117">Requirements</span></span>  
 <span data-ttu-id="7c51d-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c51d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c51d-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="7c51d-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7c51d-120">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7c51d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c51d-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c51d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c51d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c51d-122">See also</span></span>

- [<span data-ttu-id="7c51d-123">GetHashFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="7c51d-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="7c51d-124">GetHashFromFileW (método)</span><span class="sxs-lookup"><span data-stu-id="7c51d-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="7c51d-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c51d-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
