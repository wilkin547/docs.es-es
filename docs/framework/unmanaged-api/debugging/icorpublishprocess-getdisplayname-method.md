---
title: ICorPublishProcess::GetDisplayName (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6e7aa845f104ef734f039d46e1eeaba5fd01c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704094"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="0f056-102">ICorPublishProcess::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="0f056-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="0f056-103">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso que hace referencia esta [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0f056-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f056-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f056-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f056-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f056-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0f056-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="0f056-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0f056-107">[out] El número de caracteres anchos que se devuelven en el `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="0f056-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="0f056-108">[out] Una matriz para almacenar el nombre, incluida la ruta de acceso completa del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="0f056-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="0f056-109">El nombre termina en null.</span><span class="sxs-lookup"><span data-stu-id="0f056-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f056-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f056-110">Requirements</span></span>  
 <span data-ttu-id="0f056-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f056-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f056-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0f056-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0f056-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f056-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f056-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f056-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f056-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f056-115">See also</span></span>

- [<span data-ttu-id="0f056-116">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f056-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
