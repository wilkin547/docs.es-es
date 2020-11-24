---
title: EnumerateCLRs (Función)
ms.date: 03/30/2017
api_name:
- EnumerateCLRs
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type:
- apiref
ms.openlocfilehash: 8fe0df3ee08f9915ed43990b6f9686e25b183a0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676106"
---
# <a name="enumerateclrs-function"></a><span data-ttu-id="dc9aa-102">EnumerateCLRs (Función)</span><span class="sxs-lookup"><span data-stu-id="dc9aa-102">EnumerateCLRs Function</span></span>

<span data-ttu-id="dc9aa-103">Proporciona un mecanismo para enumerar los CLR de un proceso.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-103">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc9aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc9aa-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc9aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc9aa-105">Parameters</span></span>  

 `debuggeePID`  
 <span data-ttu-id="dc9aa-106">[in] Identificador del proceso desde el que se van a enumerar los CLR cargados.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-106">[in] Process identifier of the process from which loaded CLRs will be enumerated.</span></span>  
  
 `ppHandleArrayOut`  
 <span data-ttu-id="dc9aa-107">[out] Puntero a una matriz que contiene identificadores de evento que se usan para continuar el inicio de un CLR.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-107">[out] Pointer to an array containing event handles that are used to continue a CLR startup.</span></span> <span data-ttu-id="dc9aa-108">No se garantiza que todos los identificadores de la matriz sean válidos.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-108">Each handle in the array is not guaranteed to be valid.</span></span> <span data-ttu-id="dc9aa-109">Si es válido, el identificador se usará como evento de inicio continuo para el tiempo de ejecución correspondiente ubicado en el mismo índice de `ppStringArrayOut`.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-109">If valid, the handle is to be used as the continue-startup event for the corresponding runtime located in the same index of `ppStringArrayOut`.</span></span>  
  
 `ppStringArrayOut`  
 <span data-ttu-id="dc9aa-110">[out] Puntero a una matriz de cadenas que especifican las rutas de acceso completas a los CLR cargados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-110">[out] Pointer to an array of strings that specify full paths to CLRs loaded in the process.</span></span>  
  
 `pdwArrayLengthOut`  
 <span data-ttu-id="dc9aa-111">[out] Puntero a una DWORD que contiene la longitud de `ppHandleArrayOut` y `pdwArrayLengthOut` de igual tamaño.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-111">[out] Pointer to a DWORD that contains the length of the equally sized `ppHandleArrayOut` and `pdwArrayLengthOut`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc9aa-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dc9aa-112">Return Value</span></span>  

 <span data-ttu-id="dc9aa-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc9aa-113">S_OK</span></span>  
 <span data-ttu-id="dc9aa-114">Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-114">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="dc9aa-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dc9aa-115">E_INVALIDARG</span></span>  
 <span data-ttu-id="dc9aa-116">`ppHandleArrayOut` o `ppStringArrayOut` es NULL, o `pdwArrayLengthOut` es NULL.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-116">Either `ppHandleArrayOut` or `ppStringArrayOut` is null, or `pdwArrayLengthOut` is null.</span></span>  
  
 <span data-ttu-id="dc9aa-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dc9aa-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="dc9aa-118">La función no puede asignar suficiente memoria para las matrices de identificadores y rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-118">The function is unable to allocate enough memory for the handle and path arrays.</span></span>  
  
 <span data-ttu-id="dc9aa-119">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="dc9aa-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="dc9aa-120">No se pueden enumerar los CLR cargados.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-120">Unable to enumerate loaded CLRs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc9aa-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc9aa-121">Remarks</span></span>  

 <span data-ttu-id="dc9aa-122">Para un proceso de destino identificado por `debuggeePID`, la función devuelve una matriz de rutas de acceso, `ppStringArrayOut`, a los CLR cargados en el proceso; una matriz de identificadores de eventos, `ppHandleArrayOut`, que puede contener un evento de inicio continuo para el CLR en el mismo índice; y el tamaño de las matrices, `pdwArrayLengthOut`, que especifica el número de CLR que hay cargados.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-122">For a target process that is identified by `debuggeePID`, the function returns an array of paths, `ppStringArrayOut`, to CLRs loaded in the process; an array of event handles, `ppHandleArrayOut`, which may contain a continue-startup event for the CLR at the same index; and the size of the arrays, `pdwArrayLengthOut`, which specifies the number of CLRs that are loaded.</span></span>  
  
 <span data-ttu-id="dc9aa-123">En el sistema operativo Windows, `debuggeePID` se asigna a un identificador de procesos del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-123">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="dc9aa-124">Esta función asigna la memoria para `ppHandleArrayOut` y `ppStringArrayOut`.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-124">The memory for `ppHandleArrayOut` and `ppStringArrayOut` are allocated by this function.</span></span> <span data-ttu-id="dc9aa-125">Para liberar la memoria asignada, debe llamar a la [función closeclrenumeration (](closeclrenumeration-function.md).</span><span class="sxs-lookup"><span data-stu-id="dc9aa-125">To free the memory allocated, you must call [CloseCLREnumeration Function](closeclrenumeration-function.md).</span></span>  
  
 <span data-ttu-id="dc9aa-126">Se puede llamar a esta función con ambos parámetros de matriz establecidos en NULL para devolver el número de los CLR en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-126">This function can be called with both array parameters set to null in order to return the count of CLRs in the target process.</span></span> <span data-ttu-id="dc9aa-127">A partir de este número, un llamador puede deducir el tamaño del búfer que se creará: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span><span class="sxs-lookup"><span data-stu-id="dc9aa-127">From this count, a caller can infer the size of the buffer that will be created: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc9aa-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc9aa-128">Requirements</span></span>  

 <span data-ttu-id="dc9aa-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc9aa-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc9aa-130">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="dc9aa-130">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="dc9aa-131">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="dc9aa-131">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="dc9aa-132">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="dc9aa-132">**.NET Framework Versions:** 3.5 SP1</span></span>
