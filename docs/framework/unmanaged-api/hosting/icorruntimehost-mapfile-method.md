---
title: "ICorRuntimeHost::MapFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.MapFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd156aac23cdca446bcf2666ce36e91fef6d5392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="2df02-102">ICorRuntimeHost::MapFile (Método)</span><span class="sxs-lookup"><span data-stu-id="2df02-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="2df02-103">Asigna el archivo especificado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="2df02-103">Maps the specified file into memory.</span></span> <span data-ttu-id="2df02-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2df02-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df02-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2df02-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2df02-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2df02-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="2df02-107">[in] El identificador del archivo que se puede asignar.</span><span class="sxs-lookup"><span data-stu-id="2df02-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="2df02-108">[out] La dirección de memoria inicial donde comienza el archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="2df02-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df02-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2df02-109">Requirements</span></span>  
 <span data-ttu-id="2df02-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df02-111">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2df02-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2df02-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2df02-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2df02-113">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2df02-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df02-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df02-114">See Also</span></span>  
 [<span data-ttu-id="2df02-115">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2df02-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
