---
title: GetHashFromAssemblyFile (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f984d44d0a8acb85562a58653dfd2882053a0ce
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799280"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="1bb3c-102">GetHashFromAssemblyFile (Función)</span><span class="sxs-lookup"><span data-stu-id="1bb3c-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="1bb3c-103">Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="1bb3c-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-104">This function has been deprecated.</span></span> <span data-ttu-id="1bb3c-105">Use el método [ICLRStrongName:: gethashfromassemblyfile (](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb3c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bb3c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bb3c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bb3c-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="1bb3c-108">de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1bb3c-109">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1bb3c-110">Use cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1bb3c-111">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1bb3c-112">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1bb3c-113">enuncia El tamaño devuelto, en bytes, `pbHash`de.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bb3c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bb3c-114">Requirements</span></span>  
 <span data-ttu-id="1bb3c-115">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bb3c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bb3c-116">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="1bb3c-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1bb3c-117">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1bb3c-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1bb3c-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bb3c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb3c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb3c-119">See also</span></span>

- [<span data-ttu-id="1bb3c-120">GetHashFromAssemblyFile (método)</span><span class="sxs-lookup"><span data-stu-id="1bb3c-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="1bb3c-121">GetHashFromAssemblyFileW (método)</span><span class="sxs-lookup"><span data-stu-id="1bb3c-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="1bb3c-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bb3c-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
