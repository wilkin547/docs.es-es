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
ms.openlocfilehash: 30aad6fc62c8fee7448163ca69117b804203d505
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456487"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="2b5c5-102">GetHashFromHandle (Función)</span><span class="sxs-lookup"><span data-stu-id="2b5c5-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="2b5c5-103">Genera un hash sobre el contenido del archivo con el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="2b5c5-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-104">This function has been deprecated.</span></span> <span data-ttu-id="2b5c5-105">Use la [ICLRStrongName:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b5c5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b5c5-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b5c5-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b5c5-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="2b5c5-108">[in] El identificador del archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2b5c5-109">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="2b5c5-110">Utilice un cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2b5c5-111">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2b5c5-112">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2b5c5-113">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="2b5c5-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b5c5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b5c5-114">Requirements</span></span>  
 <span data-ttu-id="2b5c5-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b5c5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b5c5-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2b5c5-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2b5c5-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b5c5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b5c5-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b5c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b5c5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b5c5-119">See Also</span></span>  
 [<span data-ttu-id="2b5c5-120">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="2b5c5-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="2b5c5-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b5c5-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
