---
title: ICorProfilerInfo::GetClassIDInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: 4b9c577fab91e9527a1edc6c93e0618c8fe4e662
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864081"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="795cb-102">ICorProfilerInfo::GetClassIDInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="795cb-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="795cb-103">Obtiene el módulo primario y el token de metadatos para la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="795cb-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="795cb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="795cb-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="795cb-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="795cb-106">de IDENTIFICADOR de la clase para la que se va a obtener la información.</span><span class="sxs-lookup"><span data-stu-id="795cb-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="795cb-107">enuncia Puntero al identificador del módulo primario de la clase.</span><span class="sxs-lookup"><span data-stu-id="795cb-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="795cb-108">enuncia Puntero al símbolo (token) de metadatos para la clase.</span><span class="sxs-lookup"><span data-stu-id="795cb-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="795cb-109">Notas</span><span class="sxs-lookup"><span data-stu-id="795cb-109">Remarks</span></span>  
 <span data-ttu-id="795cb-110">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de metadatos para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="795cb-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="795cb-111">Después, el token de metadatos que se devuelve a la ubicación a la que `pTypeDefToken` hace referencia puede usarse para acceder a los metadatos de la clase.</span><span class="sxs-lookup"><span data-stu-id="795cb-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="795cb-112">Para obtener más información sobre los tipos genéricos, use [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="795cb-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="795cb-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="795cb-113">Requirements</span></span>  
 <span data-ttu-id="795cb-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="795cb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="795cb-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="795cb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="795cb-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="795cb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="795cb-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="795cb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795cb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="795cb-118">See also</span></span>

- [<span data-ttu-id="795cb-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="795cb-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
