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
ms.openlocfilehash: af1d0e2039024a51341e30bec497c581a0bcacb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673675"
---
# <a name="_corexemain-function"></a><span data-ttu-id="c1692-102">_CorExeMain (Función)</span><span class="sxs-lookup"><span data-stu-id="c1692-102">_CorExeMain Function</span></span>

<span data-ttu-id="c1692-103">Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1692-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1692-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1692-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c1692-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1692-105">Remarks</span></span>  

 <span data-ttu-id="c1692-106">El cargador llama a esta función en los procesos creados a partir de ensamblados ejecutables administrados.</span><span class="sxs-lookup"><span data-stu-id="c1692-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="c1692-107">En el caso de los ensamblados DLL, el cargador llama a la función [_CorDllMain](cordllmain-function.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c1692-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="c1692-108">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="c1692-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="c1692-109">En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorExeMain` función se llama indirectamente a través de una corrección en el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c1692-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="c1692-110">En todas las demás versiones de Windows, el cargador del sistema operativo lo llama directamente.</span><span class="sxs-lookup"><span data-stu-id="c1692-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="c1692-111">Para obtener más información, vea la sección Comentarios del tema [_CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="c1692-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1692-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1692-112">Requirements</span></span>  

 <span data-ttu-id="c1692-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1692-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1692-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c1692-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1692-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1692-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1692-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1692-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1692-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1692-117">See also</span></span>

- [<span data-ttu-id="c1692-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="c1692-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
