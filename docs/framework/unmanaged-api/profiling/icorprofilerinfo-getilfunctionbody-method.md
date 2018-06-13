---
title: ICorProfilerInfo::GetILFunctionBody (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bde194023ff6913db9a56e30eddaad8d7abc5ad1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452812"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="28419-102">ICorProfilerInfo::GetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="28419-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="28419-103">Obtiene un puntero al cuerpo de un método en el código de lenguaje intermedio (MSIL) de Microsoft, comenzando por su encabezado.</span><span class="sxs-lookup"><span data-stu-id="28419-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28419-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28419-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28419-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28419-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="28419-106">[in] El identificador del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="28419-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="28419-107">[in] El token de metadatos para el método.</span><span class="sxs-lookup"><span data-stu-id="28419-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="28419-108">[out] Un puntero al encabezado del método.</span><span class="sxs-lookup"><span data-stu-id="28419-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="28419-109">[out] Un entero que especifica el tamaño del método.</span><span class="sxs-lookup"><span data-stu-id="28419-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28419-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28419-110">Remarks</span></span>  
 <span data-ttu-id="28419-111">Un método tiene un ámbito por el módulo en el que reside.</span><span class="sxs-lookup"><span data-stu-id="28419-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="28419-112">Dado que el `GetILFunctionBody` método está diseñado para proporcionar acceso de herramientas al código MSIL antes de que se ha cargado por common language runtime (CLR), que utiliza el token de metadatos del método para buscar la instancia deseada.</span><span class="sxs-lookup"><span data-stu-id="28419-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="28419-113">`GetILFunctionBody` puede devolver un HRESULT de CORPROF_E_FUNCTION_NOT_IL si la `methodId` señala a un método sin código MSIL (como un método abstracto o una plataforma de invocación de método (PInvoke)).</span><span class="sxs-lookup"><span data-stu-id="28419-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28419-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28419-114">Requirements</span></span>  
 <span data-ttu-id="28419-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28419-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28419-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28419-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28419-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28419-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28419-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28419-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28419-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="28419-119">See Also</span></span>  
 [<span data-ttu-id="28419-120">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28419-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
