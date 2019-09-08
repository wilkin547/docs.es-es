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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e79c1d89d767832022d487681e0515e5e92a7f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799218"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="08638-102">GetHashFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="08638-102">GetHashFromFile Function</span></span>
<span data-ttu-id="08638-103">Genera un hash a partir del contenido del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="08638-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="08638-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="08638-104">This function has been deprecated.</span></span> <span data-ttu-id="08638-105">Use el método [ICLRStrongName:: gethashfromfile (](../hosting/iclrstrongname-gethashfromfile-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="08638-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08638-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08638-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08638-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08638-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="08638-108">de Nombre del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="08638-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="08638-109">[in, out] Algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="08638-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="08638-110">Los algoritmos válidos son los definidos por la CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="08638-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="08638-111">Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="08638-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="08638-112">enuncia Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="08638-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="08638-113">de Tamaño máximo del búfer al que `pbHash` apunta.</span><span class="sxs-lookup"><span data-stu-id="08638-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="08638-114">enuncia Tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="08638-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08638-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08638-115">Remarks</span></span>  
 <span data-ttu-id="08638-116">Esta función es igual que [GetHashFromFileW (](gethashfromfilew-function.md), salvo que la especificación de nombre de archivo es ANSI en lugar de Unicode.</span><span class="sxs-lookup"><span data-stu-id="08638-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08638-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08638-117">Requirements</span></span>  
 <span data-ttu-id="08638-118">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08638-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08638-119">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="08638-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="08638-120">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="08638-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08638-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08638-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08638-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="08638-122">See also</span></span>

- [<span data-ttu-id="08638-123">GetHashFromFile (método)</span><span class="sxs-lookup"><span data-stu-id="08638-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="08638-124">GetHashFromFileW (método)</span><span class="sxs-lookup"><span data-stu-id="08638-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="08638-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08638-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
