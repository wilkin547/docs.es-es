---
description: 'Más información acerca de: ICorRuntimeHost:: MapFile (método)'
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
ms.openlocfilehash: 80c01a036de83b32b9d0de745d76bb97825c980b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789637"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="7bf4e-103">ICorRuntimeHost::MapFile (Método)</span><span class="sxs-lookup"><span data-stu-id="7bf4e-103">ICorRuntimeHost::MapFile Method</span></span>

<span data-ttu-id="7bf4e-104">Asigna el archivo especificado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="7bf4e-104">Maps the specified file into memory.</span></span> <span data-ttu-id="7bf4e-105">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="7bf4e-105">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf4e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bf4e-106">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bf4e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bf4e-107">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="7bf4e-108">de Identificador del archivo que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="7bf4e-108">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="7bf4e-109">enuncia Dirección de memoria de inicio en la que se va a empezar a asignar el archivo.</span><span class="sxs-lookup"><span data-stu-id="7bf4e-109">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf4e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bf4e-110">Requirements</span></span>  

 <span data-ttu-id="7bf4e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bf4e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf4e-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7bf4e-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bf4e-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bf4e-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bf4e-114">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="7bf4e-114">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf4e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bf4e-115">See also</span></span>

- [<span data-ttu-id="7bf4e-116">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bf4e-116">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
