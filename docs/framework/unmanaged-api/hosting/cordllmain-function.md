---
title: "_CorDllMain (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2e4188f8b95141118e4bbb2df2a702ff04c2adf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordllmain-function"></a><span data-ttu-id="11a0a-102">_CorDllMain (Función)</span><span class="sxs-lookup"><span data-stu-id="11a0a-102">_CorDllMain Function</span></span>
<span data-ttu-id="11a0a-103">Inicializa common language runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado de la DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="11a0a-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a0a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11a0a-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11a0a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11a0a-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="11a0a-106">[in] El identificador de instancia del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="11a0a-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="11a0a-107">[in] Indica por qué se llama a la función de punto de entrada DLL.</span><span class="sxs-lookup"><span data-stu-id="11a0a-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="11a0a-108">Este parámetro puede ser uno de los valores siguientes: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH o DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="11a0a-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="11a0a-109">Para obtener descripciones de estos valores, consulte el `DllMain` documentación de Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="11a0a-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="11a0a-110">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="11a0a-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a0a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11a0a-111">Return Value</span></span>  
 <span data-ttu-id="11a0a-112">Este método devuelve `true` para el éxito y `false` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="11a0a-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11a0a-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11a0a-113">Remarks</span></span>  
 <span data-ttu-id="11a0a-114">El cargador del sistema operativo llama a esta función para los ensamblados DLL.</span><span class="sxs-lookup"><span data-stu-id="11a0a-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="11a0a-115">Para los ensamblados ejecutables, el cargador llama a la [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funcione en su lugar.</span><span class="sxs-lookup"><span data-stu-id="11a0a-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="11a0a-116">El cargador del sistema operativo llama a este método sin tener en cuenta el punto de entrada especificado en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="11a0a-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="11a0a-117">En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorDllMain` función se llama indirectamente a través de un fixupin el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="11a0a-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="11a0a-118">En las demás versiones de Windows, se llama directamente por el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="11a0a-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="11a0a-119">Para obtener más información, vea la sección comentarios en el [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tema.</span><span class="sxs-lookup"><span data-stu-id="11a0a-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a0a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11a0a-120">Requirements</span></span>  
 <span data-ttu-id="11a0a-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a0a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a0a-122">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11a0a-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11a0a-123">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11a0a-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11a0a-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a0a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a0a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="11a0a-125">See Also</span></span>  
 [<span data-ttu-id="11a0a-126">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="11a0a-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
