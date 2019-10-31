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
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136974"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="e31bf-102">\_función CorDllMain</span><span class="sxs-lookup"><span data-stu-id="e31bf-102">\_CorDllMain Function</span></span>

<span data-ttu-id="e31bf-103">Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="e31bf-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e31bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e31bf-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e31bf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e31bf-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="e31bf-106">de Identificador de instancia del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="e31bf-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="e31bf-107">de Indica por qué se llama a la función de punto de entrada del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="e31bf-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="e31bf-108">Este parámetro puede ser uno de los siguientes valores: DLL\_PROCESS_ATTACH, DLL\_subproceso\_adjuntar, DLL\_subproceso\_adjuntar o DLL\_procesar\_desasociar.</span><span class="sxs-lookup"><span data-stu-id="e31bf-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="e31bf-109">Para obtener descripciones de estos valores, consulte la documentación de `DllMain` en el SDK de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e31bf-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="e31bf-110">de Sin usar.</span><span class="sxs-lookup"><span data-stu-id="e31bf-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e31bf-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e31bf-111">Return Value</span></span>  
 <span data-ttu-id="e31bf-112">Este método devuelve `true` para Success y `false` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="e31bf-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e31bf-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e31bf-113">Remarks</span></span>  
 <span data-ttu-id="e31bf-114">El cargador del sistema operativo llama a esta función para los ensamblados DLL.</span><span class="sxs-lookup"><span data-stu-id="e31bf-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="e31bf-115">En el caso de los ensamblados ejecutables, el cargador llama a la función [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e31bf-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="e31bf-116">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="e31bf-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="e31bf-117">El cargador del sistema operativo llama directamente a la función `_CorDllMain`.</span><span class="sxs-lookup"><span data-stu-id="e31bf-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="e31bf-118">Para obtener más información, vea la sección Comentarios del tema [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e31bf-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e31bf-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e31bf-119">Requirements</span></span>  

 <span data-ttu-id="e31bf-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e31bf-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e31bf-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e31bf-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e31bf-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e31bf-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e31bf-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e31bf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e31bf-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e31bf-124">See also</span></span>

- [<span data-ttu-id="e31bf-125">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="e31bf-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
