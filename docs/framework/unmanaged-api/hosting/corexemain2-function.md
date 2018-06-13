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
ms.openlocfilehash: 573336b32040f44ff1b59fcbb75b59aa00976b5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430184"
---
# <a name="corexemain2-function"></a><span data-ttu-id="cf817-102">_CorExeMain2 (Función)</span><span class="sxs-lookup"><span data-stu-id="cf817-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="cf817-103">Ejecuta el punto de entrada en el código asignado a la memoria especificado.</span><span class="sxs-lookup"><span data-stu-id="cf817-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="cf817-104">Esta función se invoca por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cf817-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf817-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf817-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf817-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf817-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="cf817-107">[in] Un puntero al código asignado a la memoria.</span><span class="sxs-lookup"><span data-stu-id="cf817-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="cf817-108">[in] El número de elementos `pUnmappedPE` puede contener.</span><span class="sxs-lookup"><span data-stu-id="cf817-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="cf817-109">[in] Un puntero al nombre de la imagen ejecutable.</span><span class="sxs-lookup"><span data-stu-id="cf817-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="cf817-110">[in] El nombre del archivo del cargador.</span><span class="sxs-lookup"><span data-stu-id="cf817-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="cf817-111">[in] Parámetros de línea de comandos, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="cf817-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf817-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf817-112">Requirements</span></span>  
 <span data-ttu-id="cf817-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf817-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf817-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf817-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf817-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf817-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf817-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf817-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf817-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf817-117">See Also</span></span>  
 [<span data-ttu-id="cf817-118">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="cf817-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
