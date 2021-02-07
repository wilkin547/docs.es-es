---
description: 'Más información acerca de: _CorExeMain función'
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
ms.openlocfilehash: f94197598d01255c35712aa682f83ca9be1fb377
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717139"
---
# <a name="_corexemain-function"></a><span data-ttu-id="73f38-103">_CorExeMain (Función)</span><span class="sxs-lookup"><span data-stu-id="73f38-103">_CorExeMain Function</span></span>

<span data-ttu-id="73f38-104">Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="73f38-104">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f38-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73f38-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="73f38-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73f38-106">Remarks</span></span>  

 <span data-ttu-id="73f38-107">El cargador llama a esta función en los procesos creados a partir de ensamblados ejecutables administrados.</span><span class="sxs-lookup"><span data-stu-id="73f38-107">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="73f38-108">En el caso de los ensamblados DLL, el cargador llama a la función [_CorDllMain](cordllmain-function.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="73f38-108">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="73f38-109">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="73f38-109">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="73f38-110">En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorExeMain` función se llama indirectamente a través de una corrección en el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="73f38-110">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="73f38-111">En todas las demás versiones de Windows, el cargador del sistema operativo lo llama directamente.</span><span class="sxs-lookup"><span data-stu-id="73f38-111">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="73f38-112">Para obtener más información, vea la sección Comentarios del tema [_CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="73f38-112">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73f38-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73f38-113">Requirements</span></span>  

 <span data-ttu-id="73f38-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73f38-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f38-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="73f38-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73f38-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73f38-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73f38-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f38-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f38-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="73f38-118">See also</span></span>

- [<span data-ttu-id="73f38-119">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="73f38-119">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
