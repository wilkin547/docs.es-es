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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c515a8184e8c01b0e292057f3f66ffef28f2c5fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402886"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="c9e70-102">ICLRDataTarget::GetMachineType (Método)</span><span class="sxs-lookup"><span data-stu-id="c9e70-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="c9e70-103">Obtiene el identificador para el tipo de conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c9e70-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9e70-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9e70-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9e70-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="c9e70-106">[out] Está utilizando un puntero a un valor que indica que el conjunto de instrucciones que el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c9e70-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="c9e70-107">El valor devuelto `machineType` es una de las constantes IMAGE_FILE_MACHINE, que se definen en el archivo de encabezado WinNT.h.</span><span class="sxs-lookup"><span data-stu-id="c9e70-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9e70-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9e70-108">Requirements</span></span>  
 <span data-ttu-id="c9e70-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9e70-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9e70-110">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c9e70-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c9e70-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9e70-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9e70-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9e70-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e70-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9e70-113">See Also</span></span>  
 [<span data-ttu-id="c9e70-114">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9e70-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
