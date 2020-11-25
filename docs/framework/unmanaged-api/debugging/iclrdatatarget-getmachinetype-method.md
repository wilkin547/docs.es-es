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
ms.openlocfilehash: 00601e0bc722c0dc5e972324eddc0ab073d04586
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703543"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="cfee8-102">ICLRDataTarget::GetMachineType (Método)</span><span class="sxs-lookup"><span data-stu-id="cfee8-102">ICLRDataTarget::GetMachineType Method</span></span>

<span data-ttu-id="cfee8-103">Obtiene el identificador del tipo de conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="cfee8-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfee8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfee8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfee8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfee8-105">Parameters</span></span>  

 `machineType`  
 <span data-ttu-id="cfee8-106">enuncia Un puntero a un valor que indica el conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="cfee8-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="cfee8-107">El devuelto `machineType` es una de las constantes de IMAGE_FILE_MACHINE, que se definen en el archivo de encabezado Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="cfee8-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfee8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfee8-108">Requirements</span></span>  

 <span data-ttu-id="cfee8-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfee8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfee8-110">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="cfee8-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cfee8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfee8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfee8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfee8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfee8-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfee8-113">See also</span></span>

- [<span data-ttu-id="cfee8-114">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfee8-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
