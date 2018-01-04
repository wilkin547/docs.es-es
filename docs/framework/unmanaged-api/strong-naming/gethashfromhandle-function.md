---
title: "GetHashFromHandle (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromHandle
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromHandle
helpviewer_keywords: GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45acc02645f45446e37935d7fe7a455f4105d8bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="bad3b-102">GetHashFromHandle (Función)</span><span class="sxs-lookup"><span data-stu-id="bad3b-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="bad3b-103">Genera un hash sobre el contenido del archivo con el identificador de archivo especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="bad3b-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="bad3b-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="bad3b-104">This function has been deprecated.</span></span> <span data-ttu-id="bad3b-105">Use la [ICLRStrongName:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bad3b-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad3b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bad3b-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bad3b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bad3b-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="bad3b-108">[in] El identificador del archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bad3b-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="bad3b-109">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="bad3b-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="bad3b-110">Utilice un cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bad3b-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="bad3b-111">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="bad3b-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="bad3b-112">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bad3b-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="bad3b-113">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bad3b-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad3b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bad3b-114">Requirements</span></span>  
 <span data-ttu-id="bad3b-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad3b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad3b-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bad3b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bad3b-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bad3b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bad3b-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad3b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad3b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bad3b-119">See Also</span></span>  
 [<span data-ttu-id="bad3b-120">GetHashFromHandle (método)</span><span class="sxs-lookup"><span data-stu-id="bad3b-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="bad3b-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bad3b-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
