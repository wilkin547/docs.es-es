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
ms.openlocfilehash: fcf0ab73c79a5fa116a89cdfcc2e73b17d9eabfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785492"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="3fed1-102">ICLRDataTarget::GetImageBase (Método)</span><span class="sxs-lookup"><span data-stu-id="3fed1-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="3fed1-103">Obtiene la dirección de memoria base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="3fed1-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fed1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fed1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fed1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3fed1-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="3fed1-106">de Nombre de archivo de la imagen, incluida su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3fed1-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="3fed1-107">enuncia Puntero a un CLRDATA_ADDRESS que almacena la dirección base de la imagen.</span><span class="sxs-lookup"><span data-stu-id="3fed1-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fed1-108">Notas</span><span class="sxs-lookup"><span data-stu-id="3fed1-108">Remarks</span></span>  
 <span data-ttu-id="3fed1-109">El nombre del archivo de imagen puede tener o no una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3fed1-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="3fed1-110">Si se especifica una ruta de acceso, la coincidencia se realiza en toda la ruta de acceso; de lo contrario, la búsqueda de coincidencias se realiza solo en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="3fed1-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fed1-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3fed1-111">Requirements</span></span>  
 <span data-ttu-id="3fed1-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fed1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fed1-113">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="3fed1-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3fed1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fed1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fed1-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fed1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fed1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fed1-116">See also</span></span>

- [<span data-ttu-id="3fed1-117">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fed1-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
