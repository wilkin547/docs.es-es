---
description: 'Más información acerca de: ICLRDataTarget:: GetPointerSize ((método)'
title: ICLRDataTarget::GetPointerSize (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: 4c6e5ab9b919d1c5d2d6e2267a48d46a11cccc09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801337"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="dea70-103">ICLRDataTarget::GetPointerSize (Método)</span><span class="sxs-lookup"><span data-stu-id="dea70-103">ICLRDataTarget::GetPointerSize Method</span></span>

<span data-ttu-id="dea70-104">Obtiene el tamaño, en bytes, del tipo de puntero que utiliza el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dea70-104">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="dea70-105">El servicio de acceso a datos de Common Language Runtime llama a este método.</span><span class="sxs-lookup"><span data-stu-id="dea70-105">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dea70-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dea70-106">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dea70-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dea70-107">Parameters</span></span>  

 `pointerSize`  
 <span data-ttu-id="dea70-108">enuncia Un puntero a un valor entero que especifica el tamaño, en bytes, de un puntero en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dea70-108">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dea70-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dea70-109">Remarks</span></span>  

 <span data-ttu-id="dea70-110">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="dea70-110">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dea70-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dea70-111">Requirements</span></span>  

 <span data-ttu-id="dea70-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dea70-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dea70-113">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="dea70-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dea70-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dea70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dea70-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dea70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea70-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dea70-116">See also</span></span>

- [<span data-ttu-id="dea70-117">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dea70-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
