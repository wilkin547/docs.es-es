---
title: GetHashFromHandle (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: dc241324f5844610d7b86b7cb9668f84d4525395
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140664"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="54bbf-102">GetHashFromHandle (Función)</span><span class="sxs-lookup"><span data-stu-id="54bbf-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="54bbf-103">Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="54bbf-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="54bbf-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="54bbf-104">This function has been deprecated.</span></span> <span data-ttu-id="54bbf-105">Use el método [ICLRStrongName:: gethashfromhandle (](../hosting/iclrstrongname-gethashfromhandle-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="54bbf-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54bbf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54bbf-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54bbf-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54bbf-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="54bbf-108">de Identificador del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="54bbf-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="54bbf-109">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="54bbf-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="54bbf-110">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="54bbf-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="54bbf-111">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="54bbf-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="54bbf-112">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="54bbf-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="54bbf-113">enuncia Tamaño, en bytes, del `pbHash`devuelto.</span><span class="sxs-lookup"><span data-stu-id="54bbf-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54bbf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54bbf-114">Requirements</span></span>  
 <span data-ttu-id="54bbf-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54bbf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54bbf-116">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="54bbf-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="54bbf-117">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="54bbf-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54bbf-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54bbf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bbf-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="54bbf-119">See also</span></span>

- [<span data-ttu-id="54bbf-120">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="54bbf-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="54bbf-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54bbf-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
