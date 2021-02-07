---
description: 'Más información acerca de: _CorExeMain2 función'
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
ms.openlocfilehash: 4629ea2f6c2ba13351c409bc382077eea926b507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717113"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="c4e53-103">_CorExeMain2 (Función)</span><span class="sxs-lookup"><span data-stu-id="c4e53-103">_CorExeMain2 Function</span></span>

<span data-ttu-id="c4e53-104">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="c4e53-104">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="c4e53-105">El cargador del sistema operativo llama a esta función.</span><span class="sxs-lookup"><span data-stu-id="c4e53-105">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e53-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4e53-106">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e53-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4e53-107">Parameters</span></span>  

 `pUnmappedPE`  
 <span data-ttu-id="c4e53-108">de Puntero al código asignado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="c4e53-108">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="c4e53-109">de Número de elementos que `pUnmappedPE` puede contener.</span><span class="sxs-lookup"><span data-stu-id="c4e53-109">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="c4e53-110">de Puntero al nombre de la imagen ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c4e53-110">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="c4e53-111">de Nombre del archivo del cargador.</span><span class="sxs-lookup"><span data-stu-id="c4e53-111">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="c4e53-112">de Parámetros de línea de comandos, si los hay.</span><span class="sxs-lookup"><span data-stu-id="c4e53-112">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e53-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4e53-113">Requirements</span></span>  

 <span data-ttu-id="c4e53-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e53-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e53-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c4e53-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4e53-116">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4e53-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4e53-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e53-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e53-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4e53-118">See also</span></span>

- [<span data-ttu-id="c4e53-119">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="c4e53-119">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
