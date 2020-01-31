---
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
ms.openlocfilehash: 50ea9caf08b2ffb689760da95af4e5c3fdd77301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793737"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="4a253-102">ICLRDataTarget::GetMachineType (Método)</span><span class="sxs-lookup"><span data-stu-id="4a253-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="4a253-103">Obtiene el identificador del tipo de conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="4a253-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a253-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a253-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a253-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4a253-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="4a253-106">enuncia Un puntero a un valor que indica el conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="4a253-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="4a253-107">El `machineType` devuelto es una de las constantes de IMAGE_FILE_MACHINE, que se definen en el archivo de encabezado Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="4a253-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a253-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4a253-108">Requirements</span></span>  
 <span data-ttu-id="4a253-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a253-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a253-110">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="4a253-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4a253-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a253-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a253-112">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a253-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a253-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a253-113">See also</span></span>

- [<span data-ttu-id="4a253-114">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a253-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
