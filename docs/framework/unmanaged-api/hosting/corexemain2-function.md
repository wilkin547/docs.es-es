---
title: _CorExeMain2 (Función)
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
ms.openlocfilehash: 8202fe4ec3ae6ef96440f203c5aea6db84744a72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616592"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="55c7b-102">_CorExeMain2 (Función)</span><span class="sxs-lookup"><span data-stu-id="55c7b-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="55c7b-103">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="55c7b-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="55c7b-104">El cargador del sistema operativo llama a esta función.</span><span class="sxs-lookup"><span data-stu-id="55c7b-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c7b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55c7b-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c7b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55c7b-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="55c7b-107">de Puntero al código asignado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="55c7b-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="55c7b-108">de Número de elementos que `pUnmappedPE` puede contener.</span><span class="sxs-lookup"><span data-stu-id="55c7b-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="55c7b-109">de Puntero al nombre de la imagen ejecutable.</span><span class="sxs-lookup"><span data-stu-id="55c7b-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="55c7b-110">de Nombre del archivo del cargador.</span><span class="sxs-lookup"><span data-stu-id="55c7b-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="55c7b-111">de Parámetros de línea de comandos, si los hay.</span><span class="sxs-lookup"><span data-stu-id="55c7b-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c7b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55c7b-112">Requirements</span></span>  
 <span data-ttu-id="55c7b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c7b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c7b-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="55c7b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55c7b-115">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55c7b-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55c7b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c7b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c7b-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="55c7b-117">See also</span></span>

- [<span data-ttu-id="55c7b-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="55c7b-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
