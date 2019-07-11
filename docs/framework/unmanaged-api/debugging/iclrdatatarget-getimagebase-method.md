---
title: ICLRDataTarget::GetImageBase (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbb655d6ed0b9bd88c5eedf61a191401a805fb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738757"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="b76ff-102">ICLRDataTarget::GetImageBase (Método)</span><span class="sxs-lookup"><span data-stu-id="b76ff-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="b76ff-103">Obtiene la dirección de memoria de base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="b76ff-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b76ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b76ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b76ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b76ff-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="b76ff-106">[in] El nombre de archivo de la imagen, incluida su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="b76ff-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="b76ff-107">[out] Un puntero a CLRDATA_ADDRESS que almacena la dirección de la imagen base.</span><span class="sxs-lookup"><span data-stu-id="b76ff-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b76ff-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b76ff-108">Remarks</span></span>  
 <span data-ttu-id="b76ff-109">El nombre de archivo de imagen puede tener o no una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="b76ff-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="b76ff-110">Si se especifica una ruta de acceso, la búsqueda de coincidencias se realiza en la ruta de acceso completa; en caso contrario, la coincidencia se realiza solo en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="b76ff-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b76ff-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b76ff-111">Requirements</span></span>  
 <span data-ttu-id="b76ff-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b76ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b76ff-113">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b76ff-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b76ff-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b76ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b76ff-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b76ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76ff-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b76ff-116">See also</span></span>

- [<span data-ttu-id="b76ff-117">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b76ff-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
