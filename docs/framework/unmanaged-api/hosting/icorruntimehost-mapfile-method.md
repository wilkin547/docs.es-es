---
title: ICorRuntimeHost::MapFile (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8a979e86dbe52577d0b58089015338e4a87750d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193881"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="1945a-102">ICorRuntimeHost::MapFile (Método)</span><span class="sxs-lookup"><span data-stu-id="1945a-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="1945a-103">Asigna el archivo especificado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="1945a-103">Maps the specified file into memory.</span></span> <span data-ttu-id="1945a-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="1945a-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1945a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1945a-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1945a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1945a-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="1945a-107">[in] El identificador del archivo que se puede asignar.</span><span class="sxs-lookup"><span data-stu-id="1945a-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="1945a-108">[out] La dirección de memoria de inicio donde comienza el archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="1945a-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1945a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1945a-109">Requirements</span></span>  
 <span data-ttu-id="1945a-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1945a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1945a-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1945a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1945a-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1945a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1945a-113">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="1945a-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1945a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1945a-114">See also</span></span>

- [<span data-ttu-id="1945a-115">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1945a-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
