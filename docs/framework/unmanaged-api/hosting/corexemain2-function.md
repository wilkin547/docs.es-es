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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f968d84ae695eb1da127538ebdc5e4f55d6ebf39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985860"
---
# <a name="corexemain2-function"></a><span data-ttu-id="696de-102">_CorExeMain2 (Función)</span><span class="sxs-lookup"><span data-stu-id="696de-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="696de-103">Ejecuta el punto de entrada en el código asignado a memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="696de-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="696de-104">El cargador del sistema operativo llama a esta función.</span><span class="sxs-lookup"><span data-stu-id="696de-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696de-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="696de-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="696de-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="696de-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="696de-107">[in] Un puntero al código asignado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="696de-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="696de-108">[in] El número de elementos `pUnmappedPE` puede contener.</span><span class="sxs-lookup"><span data-stu-id="696de-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="696de-109">[in] Un puntero al nombre de la imagen ejecutable.</span><span class="sxs-lookup"><span data-stu-id="696de-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="696de-110">[in] El nombre del archivo del cargador.</span><span class="sxs-lookup"><span data-stu-id="696de-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="696de-111">[in] Parámetros de línea de comandos, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="696de-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696de-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="696de-112">Requirements</span></span>  
 <span data-ttu-id="696de-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="696de-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696de-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="696de-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="696de-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="696de-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="696de-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696de-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696de-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="696de-117">See also</span></span>

- [<span data-ttu-id="696de-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="696de-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
