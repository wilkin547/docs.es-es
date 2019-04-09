---
title: GetHashFromFileW (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be512bab30e08ddeb7deadf8a29263e928549a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134620"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="bbe70-102">GetHashFromFileW (Función)</span><span class="sxs-lookup"><span data-stu-id="bbe70-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="bbe70-103">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="bbe70-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="bbe70-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="bbe70-104">This function has been deprecated.</span></span> <span data-ttu-id="bbe70-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bbe70-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe70-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbe70-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="bbe70-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bbe70-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="bbe70-108">[in] Nombre del archivo al hash de Unicode.</span><span class="sxs-lookup"><span data-stu-id="bbe70-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="bbe70-109">[in, out] El algoritmo que se utilizará al generar el código hash.</span><span class="sxs-lookup"><span data-stu-id="bbe70-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="bbe70-110">Los algoritmos válidos son los definidos por CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="bbe70-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="bbe70-111">Si `piHashAlg` se establece en 0, el algoritmo predeterminado CALG_SHA-1 se utiliza.</span><span class="sxs-lookup"><span data-stu-id="bbe70-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="bbe70-112">[out] Una matriz de bytes que contiene el código hash generado.</span><span class="sxs-lookup"><span data-stu-id="bbe70-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="bbe70-113">[in] El tamaño máximo del búfer señalado por `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bbe70-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="bbe70-114">[out] El tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bbe70-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbe70-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbe70-115">Remarks</span></span>  
 <span data-ttu-id="bbe70-116">Esta función es el mismo que [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), salvo que la especificación del nombre de archivo es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="bbe70-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe70-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbe70-117">Requirements</span></span>  
 <span data-ttu-id="bbe70-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbe70-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbe70-119">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bbe70-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bbe70-120">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bbe70-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="bbe70-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bbe70-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbe70-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbe70-122">See also</span></span>

- [<span data-ttu-id="bbe70-123">Método GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="bbe70-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="bbe70-124">Método GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="bbe70-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="bbe70-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbe70-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
