---
description: 'Más información acerca de: ICLRDataTarget:: GetMachineType ((método)'
title: ICLRDataTarget::GetMachineType (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
ms.openlocfilehash: 5624f734a77f51b4ea6cd9dd0c9df393c72e7d26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801350"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="b2415-103">ICLRDataTarget::GetMachineType (Método)</span><span class="sxs-lookup"><span data-stu-id="b2415-103">ICLRDataTarget::GetMachineType Method</span></span>

<span data-ttu-id="b2415-104">Obtiene el identificador del tipo de conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="b2415-104">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2415-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2415-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2415-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2415-106">Parameters</span></span>  

 `machineType`  
 <span data-ttu-id="b2415-107">enuncia Un puntero a un valor que indica el conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="b2415-107">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="b2415-108">El devuelto `machineType` es una de las constantes de IMAGE_FILE_MACHINE, que se definen en el archivo de encabezado Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="b2415-108">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2415-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2415-109">Requirements</span></span>  

 <span data-ttu-id="b2415-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2415-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2415-111">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="b2415-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b2415-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2415-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2415-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2415-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2415-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2415-114">See also</span></span>

- [<span data-ttu-id="b2415-115">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2415-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
