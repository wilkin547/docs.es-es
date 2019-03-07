---
title: _CorDllMain (Función)
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3c529e77cad16f0bde12e34491829b58add17aa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500396"
---
# <a name="cordllmain-function"></a><span data-ttu-id="7971a-102">_CorDllMain (Función)</span><span class="sxs-lookup"><span data-stu-id="7971a-102">_CorDllMain Function</span></span>
<span data-ttu-id="7971a-103">Inicializa common language runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="7971a-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7971a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7971a-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7971a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7971a-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="7971a-106">[in] El identificador de instancia del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="7971a-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="7971a-107">[in] Indica por qué se llama a la función de punto de entrada DLL.</span><span class="sxs-lookup"><span data-stu-id="7971a-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="7971a-108">Este parámetro puede ser uno de los siguientes valores: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH o DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="7971a-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="7971a-109">Para obtener descripciones de estos valores, vea el `DllMain` documentación de Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="7971a-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="7971a-110">[in] Sin usar.</span><span class="sxs-lookup"><span data-stu-id="7971a-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7971a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7971a-111">Return Value</span></span>  
 <span data-ttu-id="7971a-112">Este método devuelve `true` para el éxito y `false` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="7971a-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7971a-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7971a-113">Remarks</span></span>  
 <span data-ttu-id="7971a-114">El cargador del sistema operativo llama a esta función para los ensamblados DLL.</span><span class="sxs-lookup"><span data-stu-id="7971a-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="7971a-115">Para los ensamblados ejecutables, el cargador llama a la [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funcione en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7971a-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="7971a-116">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="7971a-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="7971a-117">El `_CorDllMain` función se llama directamente mediante el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7971a-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="7971a-118">Para obtener más información, vea la sección de comentarios en el [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tema.</span><span class="sxs-lookup"><span data-stu-id="7971a-118">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7971a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7971a-119">Requirements</span></span>  
 <span data-ttu-id="7971a-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7971a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7971a-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7971a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7971a-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7971a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7971a-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7971a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7971a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7971a-124">See also</span></span>
- [<span data-ttu-id="7971a-125">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="7971a-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
