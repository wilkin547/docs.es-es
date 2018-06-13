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
ms.openlocfilehash: 9a79133b117f3a718dd84af6c2144a6098bc79f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407251"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="4e71a-102">ICLRDataTarget::GetImageBase (Método)</span><span class="sxs-lookup"><span data-stu-id="4e71a-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="4e71a-103">Obtiene la dirección de memoria de base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="4e71a-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e71a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e71a-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e71a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e71a-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="4e71a-106">[in] El nombre de archivo de la imagen, incluida su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e71a-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="4e71a-107">[out] Un puntero a CLRDATA_ADDRESS que almacena la dirección base de la imagen.</span><span class="sxs-lookup"><span data-stu-id="4e71a-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e71a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e71a-108">Remarks</span></span>  
 <span data-ttu-id="4e71a-109">El nombre de archivo de imagen puede tener o no una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e71a-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="4e71a-110">Si se especifica una ruta de acceso, se realiza la coincidencia en la ruta de acceso completa; en caso contrario, la coincidencia se realiza únicamente en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="4e71a-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e71a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e71a-111">Requirements</span></span>  
 <span data-ttu-id="4e71a-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e71a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e71a-113">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="4e71a-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4e71a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e71a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e71a-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e71a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e71a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e71a-116">See Also</span></span>  
 [<span data-ttu-id="4e71a-117">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e71a-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
