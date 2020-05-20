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
ms.openlocfilehash: 935ac478fb966315e81fdcc004761038b28e3178
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616599"
---
# <a name="_corexemain-function"></a><span data-ttu-id="1e602-102">_CorExeMain (Función)</span><span class="sxs-lookup"><span data-stu-id="1e602-102">_CorExeMain Function</span></span>
<span data-ttu-id="1e602-103">Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado ejecutable y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e602-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e602-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e602-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1e602-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e602-105">Remarks</span></span>  
 <span data-ttu-id="1e602-106">El cargador llama a esta función en los procesos creados a partir de ensamblados ejecutables administrados.</span><span class="sxs-lookup"><span data-stu-id="1e602-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="1e602-107">En el caso de los ensamblados DLL, el cargador llama a la función [_CorDllMain](cordllmain-function.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1e602-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="1e602-108">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="1e602-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="1e602-109">En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorExeMain` función se llama indirectamente a través de una corrección en el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1e602-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="1e602-110">En todas las demás versiones de Windows, el cargador del sistema operativo lo llama directamente.</span><span class="sxs-lookup"><span data-stu-id="1e602-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="1e602-111">Para obtener más información, vea la sección Comentarios del tema [_CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1e602-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e602-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e602-112">Requirements</span></span>  
 <span data-ttu-id="1e602-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e602-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e602-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1e602-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e602-115">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1e602-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e602-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e602-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e602-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1e602-117">See also</span></span>

- [<span data-ttu-id="1e602-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="1e602-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
