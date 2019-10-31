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
ms.openlocfilehash: cc5324683daa9a02a6a89b2a3fb57ee9fd5dbe72
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136960"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="77081-102">_CorExeMain2 (Función)</span><span class="sxs-lookup"><span data-stu-id="77081-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="77081-103">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="77081-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="77081-104">El cargador del sistema operativo llama a esta función.</span><span class="sxs-lookup"><span data-stu-id="77081-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77081-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77081-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77081-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77081-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="77081-107">de Puntero al código asignado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="77081-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="77081-108">de Número de elementos `pUnmappedPE` pueden contener.</span><span class="sxs-lookup"><span data-stu-id="77081-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="77081-109">de Puntero al nombre de la imagen ejecutable.</span><span class="sxs-lookup"><span data-stu-id="77081-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="77081-110">de Nombre del archivo del cargador.</span><span class="sxs-lookup"><span data-stu-id="77081-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="77081-111">de Parámetros de línea de comandos, si los hay.</span><span class="sxs-lookup"><span data-stu-id="77081-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77081-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77081-112">Requirements</span></span>  
 <span data-ttu-id="77081-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77081-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77081-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="77081-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77081-115">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="77081-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77081-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77081-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77081-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="77081-117">See also</span></span>

- [<span data-ttu-id="77081-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="77081-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
