---
title: "_CorExeMain (Función)"
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
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f5c0909db10c7bf8e15a7af998b78e0a193a908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corexemain-function"></a><span data-ttu-id="146e6-102">_CorExeMain (Función)</span><span class="sxs-lookup"><span data-stu-id="146e6-102">_CorExeMain Function</span></span>
<span data-ttu-id="146e6-103">Inicializa common language runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="146e6-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="146e6-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="146e6-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="146e6-105">Remarks</span></span>  
 <span data-ttu-id="146e6-106">Esta función se invoca por el cargador en procesos creados a partir de ensamblados ejecutables administrados.</span><span class="sxs-lookup"><span data-stu-id="146e6-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="146e6-107">Para los ensamblados DLL, el cargador llama a la [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) funcione en su lugar.</span><span class="sxs-lookup"><span data-stu-id="146e6-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="146e6-108">El cargador del sistema operativo llama a este método sin tener en cuenta el punto de entrada especificado en el archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="146e6-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="146e6-109">En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorExeMain` función se llama indirectamente a través de una corrección en el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="146e6-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="146e6-110">En las demás versiones de Windows, se llama directamente por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="146e6-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="146e6-111">Para obtener más información, vea la sección comentarios en el [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tema.</span><span class="sxs-lookup"><span data-stu-id="146e6-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="146e6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="146e6-112">Requirements</span></span>  
 <span data-ttu-id="146e6-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="146e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="146e6-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="146e6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="146e6-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="146e6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="146e6-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="146e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146e6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="146e6-117">See Also</span></span>  
 [<span data-ttu-id="146e6-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="146e6-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
