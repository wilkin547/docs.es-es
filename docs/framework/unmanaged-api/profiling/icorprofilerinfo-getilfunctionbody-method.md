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
ms.openlocfilehash: 8e98ee26da2d78278435d90d6d04ef9771f41104
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489454"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="d0e6b-102">ICorProfilerInfo::GetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="d0e6b-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="d0e6b-103">Obtiene un puntero al cuerpo de un método en el código de lenguaje intermedio (MSIL) de Microsoft, comenzando por su encabezado.</span><span class="sxs-lookup"><span data-stu-id="d0e6b-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e6b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0e6b-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0e6b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0e6b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="d0e6b-106">[in] El identificador del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="d0e6b-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="d0e6b-107">[in] El token de metadatos para el método.</span><span class="sxs-lookup"><span data-stu-id="d0e6b-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="d0e6b-108">[out] Un puntero al encabezado del método.</span><span class="sxs-lookup"><span data-stu-id="d0e6b-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="d0e6b-109">[out] Un entero que especifica el tamaño del método.</span><span class="sxs-lookup"><span data-stu-id="d0e6b-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0e6b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0e6b-110">Remarks</span></span>  
 <span data-ttu-id="d0e6b-111">Un método se limita por el módulo en el que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d0e6b-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="d0e6b-112">Dado que el `GetILFunctionBody` método está diseñado para proporcionar un acceso a la herramienta en el código MSIL antes de que se hayan cargado por common language runtime (CLR), que utiliza el token de metadatos del método para buscar la instancia deseada.</span><span class="sxs-lookup"><span data-stu-id="d0e6b-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="d0e6b-113">`GetILFunctionBody` puede devolver un valor de HRESULT CORPROF_E_FUNCTION_NOT_IL si el `methodId` señala a un método sin código MSIL (como un método abstracto o una plataforma de invocación de método (PInvoke)).</span><span class="sxs-lookup"><span data-stu-id="d0e6b-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0e6b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0e6b-114">Requirements</span></span>  
 <span data-ttu-id="d0e6b-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0e6b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0e6b-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0e6b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0e6b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0e6b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0e6b-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0e6b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e6b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0e6b-119">See also</span></span>
- [<span data-ttu-id="d0e6b-120">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0e6b-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
