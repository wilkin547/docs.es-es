---
title: _CorExeMain (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7407db297a827004c851b904b2da8652778cb08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756421"
---
# <a name="corexemain-function"></a><span data-ttu-id="5a450-102">_CorExeMain (Función)</span><span class="sxs-lookup"><span data-stu-id="5a450-102">_CorExeMain Function</span></span>
<span data-ttu-id="5a450-103">Inicializa common language runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="5a450-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a450-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a450-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5a450-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a450-105">Remarks</span></span>  
 <span data-ttu-id="5a450-106">Esta función se invoca por el cargador en procesos creados a partir de ensamblados ejecutables administrados.</span><span class="sxs-lookup"><span data-stu-id="5a450-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="5a450-107">Para los ensamblados DLL, el cargador llama el [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) funcione en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5a450-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="5a450-108">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="5a450-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="5a450-109">En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorExeMain` función se llama indirectamente a través de una corrección en el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5a450-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="5a450-110">En todas las demás versiones de Windows, se llama directamente por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5a450-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="5a450-111">Para obtener más información, vea la sección de comentarios en el [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tema.</span><span class="sxs-lookup"><span data-stu-id="5a450-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a450-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a450-112">Requirements</span></span>  
 <span data-ttu-id="5a450-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a450-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a450-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a450-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a450-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a450-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a450-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a450-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a450-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a450-117">See also</span></span>

- [<span data-ttu-id="5a450-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="5a450-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
