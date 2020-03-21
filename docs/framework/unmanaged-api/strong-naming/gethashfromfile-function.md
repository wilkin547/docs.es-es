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
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176986"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="6aed9-102">GetHashFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="6aed9-102">GetHashFromFile Function</span></span>
<span data-ttu-id="6aed9-103">Genera un hash a partir del contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6aed9-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="6aed9-104">Esta función ha quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="6aed9-104">This function has been deprecated.</span></span> <span data-ttu-id="6aed9-105">Utilice el [método ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6aed9-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aed9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6aed9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aed9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6aed9-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="6aed9-108">[en] El nombre del archivo que se ha hash.</span><span class="sxs-lookup"><span data-stu-id="6aed9-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="6aed9-109">[adentro, fuera] El algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="6aed9-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="6aed9-110">Los algoritmos válidos son los definidos por Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="6aed9-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="6aed9-111">Si `piHashAlg` se establece en 0, se utiliza el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="6aed9-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="6aed9-112">[fuera] Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="6aed9-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="6aed9-113">[en] El tamaño máximo del `pbHash` búfer al que apunta.</span><span class="sxs-lookup"><span data-stu-id="6aed9-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="6aed9-114">[fuera] El tamaño, en bytes, `pbHash`del valor devuelto .</span><span class="sxs-lookup"><span data-stu-id="6aed9-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6aed9-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6aed9-115">Remarks</span></span>  
 <span data-ttu-id="6aed9-116">Esta función es la misma que [GetHashFromFileW](gethashfromfilew-function.md), excepto que la especificación de nombre de archivo es ANSI en lugar de Unicode.</span><span class="sxs-lookup"><span data-stu-id="6aed9-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aed9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6aed9-117">Requirements</span></span>  
 <span data-ttu-id="6aed9-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aed9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aed9-119">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6aed9-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6aed9-120">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6aed9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6aed9-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aed9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aed9-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6aed9-122">See also</span></span>

- [<span data-ttu-id="6aed9-123">Método GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="6aed9-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="6aed9-124">Método GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="6aed9-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="6aed9-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6aed9-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
