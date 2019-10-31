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
ms.openlocfilehash: bcf1b49f0576f5dbd73c001f8edff7a9ab29af22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139505"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="03f13-102">ICorRuntimeHost::MapFile (Método)</span><span class="sxs-lookup"><span data-stu-id="03f13-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="03f13-103">Asigna el archivo especificado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="03f13-103">Maps the specified file into memory.</span></span> <span data-ttu-id="03f13-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="03f13-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f13-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03f13-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03f13-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03f13-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="03f13-107">de Identificador del archivo que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="03f13-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="03f13-108">enuncia Dirección de memoria de inicio en la que se va a empezar a asignar el archivo.</span><span class="sxs-lookup"><span data-stu-id="03f13-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03f13-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03f13-109">Requirements</span></span>  
 <span data-ttu-id="03f13-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03f13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03f13-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="03f13-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03f13-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="03f13-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03f13-113">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="03f13-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f13-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="03f13-114">See also</span></span>

- [<span data-ttu-id="03f13-115">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03f13-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
