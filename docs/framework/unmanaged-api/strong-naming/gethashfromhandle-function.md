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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eac353252f5a97402cbd883895b3e397c39edd6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799182"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="e41fc-102">GetHashFromHandle (Función)</span><span class="sxs-lookup"><span data-stu-id="e41fc-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="e41fc-103">Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="e41fc-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="e41fc-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="e41fc-104">This function has been deprecated.</span></span> <span data-ttu-id="e41fc-105">Use el método [ICLRStrongName:: gethashfromhandle (](../hosting/iclrstrongname-gethashfromhandle-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e41fc-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41fc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e41fc-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e41fc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e41fc-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="e41fc-108">de Identificador del archivo al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e41fc-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e41fc-109">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="e41fc-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="e41fc-110">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e41fc-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e41fc-111">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="e41fc-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e41fc-112">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="e41fc-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e41fc-113">enuncia Tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="e41fc-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41fc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e41fc-114">Requirements</span></span>  
 <span data-ttu-id="e41fc-115">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e41fc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e41fc-116">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e41fc-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e41fc-117">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e41fc-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e41fc-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e41fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41fc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e41fc-119">See also</span></span>

- [<span data-ttu-id="e41fc-120">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="e41fc-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="e41fc-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e41fc-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
