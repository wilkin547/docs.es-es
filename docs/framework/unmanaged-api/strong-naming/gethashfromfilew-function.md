---
description: 'Más información acerca de: GetHashFromFileW ((función)'
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
ms.openlocfilehash: daebd06de02dfe936f1bdeb8697de4fe6524dce3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736573"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="864d7-103">GetHashFromFileW (Función)</span><span class="sxs-lookup"><span data-stu-id="864d7-103">GetHashFromFileW Function</span></span>

<span data-ttu-id="864d7-104">Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.</span><span class="sxs-lookup"><span data-stu-id="864d7-104">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="864d7-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="864d7-105">This function has been deprecated.</span></span> <span data-ttu-id="864d7-106">Use el método [ICLRStrongName:: GetHashFromFileW (](../hosting/iclrstrongname-gethashfromfilew-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="864d7-106">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="864d7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="864d7-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="864d7-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="864d7-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="864d7-109">de Nombre Unicode del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="864d7-109">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="864d7-110">[in, out] Algoritmo que se va a utilizar al generar el hash.</span><span class="sxs-lookup"><span data-stu-id="864d7-110">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="864d7-111">Los algoritmos válidos son los definidos por la CryptoAPI de Win32.</span><span class="sxs-lookup"><span data-stu-id="864d7-111">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="864d7-112">Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="864d7-112">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="864d7-113">enuncia Matriz de bytes que contiene el hash generado.</span><span class="sxs-lookup"><span data-stu-id="864d7-113">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="864d7-114">de Tamaño máximo del búfer al que apunta `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="864d7-114">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="864d7-115">enuncia Tamaño, en bytes, de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="864d7-115">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="864d7-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="864d7-116">Remarks</span></span>  

 <span data-ttu-id="864d7-117">Esta función es igual que [gethashfromfile (](gethashfromfile-function.md), salvo que la especificación de nombre de archivo es Unicode en lugar de ANSI.</span><span class="sxs-lookup"><span data-stu-id="864d7-117">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="864d7-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="864d7-118">Requirements</span></span>  

 <span data-ttu-id="864d7-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="864d7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="864d7-120">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="864d7-120">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="864d7-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="864d7-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="864d7-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="864d7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864d7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="864d7-123">See also</span></span>

- [<span data-ttu-id="864d7-124">Método GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="864d7-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="864d7-125">Método GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="864d7-125">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="864d7-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="864d7-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
