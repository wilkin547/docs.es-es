---
description: 'Más información acerca de: Createversionstringfrommodule ((función)'
title: CreateVersionStringFromModule (Función)
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
ms.openlocfilehash: 45ae3ec31cf77e4c96e42a58b23e1f52dcf7c54b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661550"
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="54257-103">CreateVersionStringFromModule (Función)</span><span class="sxs-lookup"><span data-stu-id="54257-103">CreateVersionStringFromModule Function</span></span>

<span data-ttu-id="54257-104">Crea una cadena de versión a partir de una ruta de acceso de Common Language Runtime (CLR) en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="54257-104">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54257-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54257-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54257-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54257-106">Parameters</span></span>  

 `pidDebuggee`  
 <span data-ttu-id="54257-107">[in] Identificador del proceso en el que se carga el CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="54257-107">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="54257-108">[in] Ruta de acceso completa o relativa al CLR de destino que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="54257-108">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="54257-109">[out] Búfer de retorno para almacenar la cadena de versión del CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="54257-109">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="54257-110">[in] Tamaño de `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="54257-110">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="54257-111">[out] Longitud de la cadena de versión devuelta por `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="54257-111">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54257-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="54257-112">Return Value</span></span>  

 <span data-ttu-id="54257-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="54257-113">S_OK</span></span>  
 <span data-ttu-id="54257-114">La cadena de versión del CLR de destino se devolvió correctamente en `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="54257-114">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="54257-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="54257-115">E_INVALIDARG</span></span>  
 <span data-ttu-id="54257-116">`szModuleName` es NULL, o bien `pBuffer` o `cchBuffer` es NULL.</span><span class="sxs-lookup"><span data-stu-id="54257-116">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="54257-117">`pBuffer` y `cchBuffer` deben ser ambos NULL o no NULL.</span><span class="sxs-lookup"><span data-stu-id="54257-117">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="54257-118">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="54257-118">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="54257-119">`pdwLength` es mayor que `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="54257-119">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="54257-120">Este puede ser el resultado esperado si pasó NULL tanto para `pBuffer` como para `cchBuffer`, y consultó el tamaño del búfer necesario usando `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="54257-120">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="54257-121">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="54257-121">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="54257-122">`szModuleName` no contiene una ruta de acceso a un CLR válido en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="54257-122">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="54257-123">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="54257-123">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="54257-124">`pidDebuggee` no hace referencia a un proceso válido, u otro error.</span><span class="sxs-lookup"><span data-stu-id="54257-124">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54257-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54257-125">Remarks</span></span>  

 <span data-ttu-id="54257-126">Esta función acepta un proceso de CLR que se identifica mediante `pidDebuggee` y una ruta de acceso de cadena especificada por `szModuleName`.</span><span class="sxs-lookup"><span data-stu-id="54257-126">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="54257-127">La cadena de versión se devuelve en el búfer al que `pBuffer` apunta.</span><span class="sxs-lookup"><span data-stu-id="54257-127">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="54257-128">Esta cadena es opaca para el usuario de la función; es decir, no tiene ningún significado intrínseco en la propia cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="54257-128">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="54257-129">Se usa únicamente en el contexto de esta función y de la [función CreateDebuggingInterfaceFromVersion (](createdebugginginterfacefromversion-function-for-silverlight.md).</span><span class="sxs-lookup"><span data-stu-id="54257-129">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="54257-130">Se debe llamar dos veces a esta función.</span><span class="sxs-lookup"><span data-stu-id="54257-130">This function should be called twice.</span></span> <span data-ttu-id="54257-131">Cuando la llame por primera vez, pase NULL tanto para `pBuffer` como para `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="54257-131">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="54257-132">Al hacerlo, el tamaño del búfer necesario para `pBuffer` se devuelve en `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="54257-132">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="54257-133">Después puede llamar a la función una segunda vez y pasar el búfer en `pBuffer` y su tamaño en `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="54257-133">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54257-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54257-134">Requirements</span></span>  

 <span data-ttu-id="54257-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54257-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54257-136">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="54257-136">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="54257-137">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="54257-137">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="54257-138">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="54257-138">**.NET Framework Versions:** 3.5 SP1</span></span>
