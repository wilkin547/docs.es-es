---
description: 'Más información acerca de: Createcordbobject ((función)'
title: CreateCordbObject (Función)
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: b6a585fc89f780b22f842127e1923414dbb8230f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801480"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="8cfd5-103">CreateCordbObject (Función)</span><span class="sxs-lookup"><span data-stu-id="8cfd5-103">CreateCordbObject Function</span></span>

<span data-ttu-id="8cfd5-104">Crea una interfaz de depurador ([ICorDebug](icordebug-interface.md)) que proporciona funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-104">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cfd5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cfd5-105">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cfd5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cfd5-106">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="8cfd5-107">[in] Versión de depuración del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-107">[in] Debugger version of the target process.</span></span> <span data-ttu-id="8cfd5-108">Este parámetro debe ser CorDebugVersion_2_0 para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-108">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="8cfd5-109">enuncia Puntero a un puntero a un objeto que se convertirá en una interfaz [ICorDebug](icordebug-interface.md) y se devolverá.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-109">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cfd5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8cfd5-110">Return Value</span></span>  

 <span data-ttu-id="8cfd5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cfd5-111">S_OK</span></span>  
 <span data-ttu-id="8cfd5-112">Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-112">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="8cfd5-113">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8cfd5-113">E_INVALIDARG</span></span>  
 <span data-ttu-id="8cfd5-114">`ppCordb` es nulo o `iDebuggerVersion` no es CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-114">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="8cfd5-115">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8cfd5-115">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="8cfd5-116">No se puede asignar memoria suficiente para `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-116">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="8cfd5-117">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="8cfd5-117">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8cfd5-118">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-118">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cfd5-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8cfd5-119">Remarks</span></span>  

 <span data-ttu-id="8cfd5-120">La interfaz [ICorDebug](icordebug-interface.md) que se devuelve en `ppCordb` es la interfaz de depuración de nivel superior para todos los servicios de depuración administrados.</span><span class="sxs-lookup"><span data-stu-id="8cfd5-120">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cfd5-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cfd5-121">Requirements</span></span>  

 <span data-ttu-id="8cfd5-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cfd5-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cfd5-123">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="8cfd5-123">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="8cfd5-124">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="8cfd5-124">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="8cfd5-125">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="8cfd5-125">**.NET Framework Versions:** 3.5 SP1</span></span>
