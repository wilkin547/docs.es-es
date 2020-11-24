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
ms.openlocfilehash: 1b3ebcabc66ee7ca29245bb02d958be311bc65fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673701"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="07566-102">\_CorDllMain función)</span><span class="sxs-lookup"><span data-stu-id="07566-102">\_CorDllMain Function</span></span>

<span data-ttu-id="07566-103">Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="07566-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07566-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07566-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07566-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07566-105">Parameters</span></span>  

 `hInst`  
 <span data-ttu-id="07566-106">de Identificador de instancia del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="07566-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="07566-107">de Indica por qué se llama a la función de punto de entrada del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="07566-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="07566-108">Este parámetro puede ser uno de los siguientes valores: DLL \_ PROCESS_ATTACH, \_ adjuntar subprocesos dll \_ , \_ adjuntar subprocesos dll \_ o \_ \_ desasociar proceso dll.</span><span class="sxs-lookup"><span data-stu-id="07566-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="07566-109">Para obtener descripciones de estos valores, consulte la `DllMain` documentación del SDK de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="07566-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="07566-110">[in] Sin utilizar.</span><span class="sxs-lookup"><span data-stu-id="07566-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07566-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="07566-111">Return Value</span></span>  

 <span data-ttu-id="07566-112">Este método devuelve `true` un resultado correcto y `false` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="07566-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07566-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07566-113">Remarks</span></span>  

 <span data-ttu-id="07566-114">El cargador del sistema operativo llama a esta función para los ensamblados DLL.</span><span class="sxs-lookup"><span data-stu-id="07566-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="07566-115">En el caso de los ensamblados ejecutables, el cargador llama a la función [ \_ CorExeMain](corexemain-function.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="07566-115">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="07566-116">El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="07566-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="07566-117">El `_CorDllMain` cargador del sistema operativo llama directamente a la función.</span><span class="sxs-lookup"><span data-stu-id="07566-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="07566-118">Para obtener más información, vea la sección Comentarios en el tema [ \_ CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="07566-118">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07566-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07566-119">Requirements</span></span>  

 <span data-ttu-id="07566-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07566-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07566-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="07566-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07566-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07566-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07566-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07566-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07566-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07566-124">See also</span></span>

- [<span data-ttu-id="07566-125">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="07566-125">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
