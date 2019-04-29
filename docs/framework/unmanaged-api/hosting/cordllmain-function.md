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
ms.openlocfilehash: c509f475d5bf0105ece9791ee3e51d21c298a31f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666928"
---
# <a name="cordllmain-function"></a><span data-ttu-id="99d55-102">\_Función CorDllMain</span><span class="sxs-lookup"><span data-stu-id="99d55-102">\_CorDllMain Function</span></span>

<span data-ttu-id="99d55-103">Inicializa common language runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="99d55-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99d55-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d55-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99d55-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="99d55-106">[in] El identificador de instancia del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="99d55-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="99d55-107">[in] Indica por qué se llama a la función de punto de entrada DLL.</span><span class="sxs-lookup"><span data-stu-id="99d55-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="99d55-108">Este parámetro puede ser uno de los siguientes valores: DLL\_PROCESS_ATTACH, DLL\_subprocesos\_ATTACH, DLL\_subprocesos\_adjuntar o DLL\_proceso\_DETACH.</span><span class="sxs-lookup"><span data-stu-id="99d55-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="99d55-109">Para obtener descripciones de estos valores, vea el `DllMain` documentación de Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="99d55-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="99d55-110">[in] Sin usar.</span><span class="sxs-lookup"><span data-stu-id="99d55-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99d55-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99d55-111">Return Value</span></span>  
 <span data-ttu-id="99d55-112">Este método devuelve `true` para el éxito y `false` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="99d55-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99d55-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99d55-113">Remarks</span></span>  
 <span data-ttu-id="99d55-114">El cargador del sistema operativo llama a esta función para los ensamblados DLL.</span><span class="sxs-lookup"><span data-stu-id="99d55-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="99d55-115">Para los ensamblados ejecutables, el cargador llama a la [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funcione en su lugar.</span><span class="sxs-lookup"><span data-stu-id="99d55-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="99d55-116">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="99d55-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="99d55-117">El `_CorDllMain` función se llama directamente mediante el cargador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="99d55-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="99d55-118">Para obtener más información, vea la sección de comentarios en el [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tema.</span><span class="sxs-lookup"><span data-stu-id="99d55-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d55-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99d55-119">Requirements</span></span>  

 <span data-ttu-id="99d55-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d55-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d55-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="99d55-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99d55-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99d55-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99d55-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d55-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d55-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="99d55-124">See also</span></span>

- [<span data-ttu-id="99d55-125">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="99d55-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
