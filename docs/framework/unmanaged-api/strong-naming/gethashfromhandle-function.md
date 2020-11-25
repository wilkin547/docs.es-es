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
ms.openlocfilehash: 904dcb707e704cfec2dba4e6587f7e3acaf7b538
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732338"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="bf96b-102">GetHashFromHandle (Función)</span><span class="sxs-lookup"><span data-stu-id="bf96b-102">GetHashFromHandle Function</span></span>

<span data-ttu-id="bf96b-103">Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="bf96b-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="bf96b-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="bf96b-104">This function has been deprecated.</span></span> <span data-ttu-id="bf96b-105">Use el método [ICLRStrongName:: gethashfromhandle (](../hosting/iclrstrongname-gethashfromhandle-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bf96b-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf96b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf96b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf96b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf96b-107">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="bf96b-108">de Identificador del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bf96b-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="bf96b-109">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bf96b-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="bf96b-110">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bf96b-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="bf96b-111">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="bf96b-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="bf96b-112">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="bf96b-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="bf96b-113">enuncia Tamaño, en bytes, del devuelto `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="bf96b-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf96b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf96b-114">Requirements</span></span>  

 <span data-ttu-id="bf96b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf96b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf96b-116">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="bf96b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bf96b-117">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf96b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf96b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf96b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf96b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf96b-119">See also</span></span>

- [<span data-ttu-id="bf96b-120">Método GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="bf96b-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="bf96b-121">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf96b-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
