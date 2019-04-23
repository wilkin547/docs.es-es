---
title: ICorProfilerInfo2::GetStaticFieldInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0106b2dd1151e302c0082b306d999ab5a1c4322
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177754"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="d7568-102">ICorProfilerInfo2::GetStaticFieldInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="d7568-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="d7568-103">Obtiene un valor que indica el tipo de estática que se aplica al campo especificado.</span><span class="sxs-lookup"><span data-stu-id="d7568-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7568-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7568-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7568-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7568-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d7568-106">[in] El identificador de la clase donde se define el campo estático.</span><span class="sxs-lookup"><span data-stu-id="d7568-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="d7568-107">[in] El token de metadatos para el campo estático.</span><span class="sxs-lookup"><span data-stu-id="d7568-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="d7568-108">[out] Un puntero a un valor de la [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeración que indica si el campo especificado es estático y, si es así, el tipo de estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="d7568-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7568-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7568-109">Remarks</span></span>  
 <span data-ttu-id="d7568-110">Esta información puede utilizarse para determinar qué función se debe llamar para obtener la dirección del campo estático.</span><span class="sxs-lookup"><span data-stu-id="d7568-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="d7568-111">El código del generador de perfiles debería comprobar los metadatos de un campo estático para asegurarse de que realmente tiene una dirección.</span><span class="sxs-lookup"><span data-stu-id="d7568-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="d7568-112">Literales estáticos (es decir, constantes) sólo existen en los metadatos y no tiene una dirección.</span><span class="sxs-lookup"><span data-stu-id="d7568-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7568-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7568-113">Requirements</span></span>  
 <span data-ttu-id="d7568-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7568-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7568-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7568-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7568-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7568-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7568-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7568-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7568-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7568-118">See also</span></span>

- [<span data-ttu-id="d7568-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7568-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="d7568-120">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7568-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
