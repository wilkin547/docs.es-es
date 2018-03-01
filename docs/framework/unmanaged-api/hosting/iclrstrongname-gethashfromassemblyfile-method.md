---
title: "ICLRStrongName::GetHashFromAssemblyFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6dcb0ca16c2ffdd8a928cec9cca44b628de34885
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="10c8b-102">ICLRStrongName::GetHashFromAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="10c8b-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="10c8b-103">Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="10c8b-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10c8b-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10c8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10c8b-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="10c8b-106">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="10c8b-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="10c8b-107">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="10c8b-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="10c8b-108">Utilice un cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10c8b-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="10c8b-109">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="10c8b-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="10c8b-110">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="10c8b-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="10c8b-111">[out] La devuelve el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="10c8b-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10c8b-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="10c8b-112">Return Value</span></span>  
 <span data-ttu-id="10c8b-113">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="10c8b-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c8b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10c8b-114">Requirements</span></span>  
 <span data-ttu-id="10c8b-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10c8b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c8b-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="10c8b-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="10c8b-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10c8b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10c8b-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10c8b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c8b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="10c8b-119">See Also</span></span>  
 [<span data-ttu-id="10c8b-120">GetHashFromAssemblyFileW (método)</span><span class="sxs-lookup"><span data-stu-id="10c8b-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="10c8b-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="10c8b-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
