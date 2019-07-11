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
ms.openlocfilehash: 354e1b0dad942534068d5fb07071ed4ac695fb49
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764887"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="7fc66-102">ICorPublishProcess::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="7fc66-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="7fc66-103">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso que hace referencia esta [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7fc66-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fc66-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fc66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7fc66-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7fc66-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="7fc66-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7fc66-107">[out] El número de caracteres anchos que se devuelven en el `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="7fc66-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="7fc66-108">[out] Una matriz para almacenar el nombre, incluida la ruta de acceso completa del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="7fc66-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="7fc66-109">El nombre termina en null.</span><span class="sxs-lookup"><span data-stu-id="7fc66-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc66-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fc66-110">Requirements</span></span>  
 <span data-ttu-id="7fc66-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc66-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc66-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="7fc66-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7fc66-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fc66-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fc66-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc66-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc66-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fc66-115">See also</span></span>

- [<span data-ttu-id="7fc66-116">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fc66-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
