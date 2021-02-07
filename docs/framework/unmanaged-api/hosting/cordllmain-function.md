---
description: 'Más información acerca de: _CorDllMain función'
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
ms.openlocfilehash: 442afae3a627eb684a86c02fbc6e546aa804b7a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717157"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="51aad-103">\_CorDllMain función)</span><span class="sxs-lookup"><span data-stu-id="51aad-103">\_CorDllMain Function</span></span>

<span data-ttu-id="51aad-104">Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="51aad-104">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51aad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51aad-105">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51aad-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51aad-106">Parameters</span></span>  

 `hInst`  
 <span data-ttu-id="51aad-107">de Identificador de instancia del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="51aad-107">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="51aad-108">de Indica por qué se llama a la función de punto de entrada del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="51aad-108">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="51aad-109">Este parámetro puede ser uno de los siguientes valores: DLL \_ PROCESS_ATTACH, \_ adjuntar subprocesos dll \_ , \_ adjuntar subprocesos dll \_ o \_ \_ desasociar proceso dll.</span><span class="sxs-lookup"><span data-stu-id="51aad-109">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="51aad-110">Para obtener descripciones de estos valores, consulte la `DllMain` documentación del SDK de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="51aad-110">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="51aad-111">[in] Sin utilizar.</span><span class="sxs-lookup"><span data-stu-id="51aad-111">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51aad-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51aad-112">Return Value</span></span>  

 <span data-ttu-id="51aad-113">Este método devuelve `true` un resultado correcto y `false` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="51aad-113">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51aad-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="51aad-114">Remarks</span></span>  

 <span data-ttu-id="51aad-115">El cargador del sistema operativo llama a esta función para los ensamblados DLL.</span><span class="sxs-lookup"><span data-stu-id="51aad-115">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="51aad-116">En el caso de los ensamblados ejecutables, el cargador llama a la función [ \_ CorExeMain](corexemain-function.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="51aad-116">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="51aad-117">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="51aad-117">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="51aad-118">El `_CorDllMain` cargador del sistema operativo llama directamente a la función.</span><span class="sxs-lookup"><span data-stu-id="51aad-118">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="51aad-119">Para obtener más información, vea la sección Comentarios en el tema [ \_ CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="51aad-119">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51aad-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51aad-120">Requirements</span></span>  

 <span data-ttu-id="51aad-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51aad-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51aad-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="51aad-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51aad-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51aad-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51aad-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51aad-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51aad-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="51aad-125">See also</span></span>

- [<span data-ttu-id="51aad-126">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="51aad-126">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
