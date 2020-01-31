---
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
ms.openlocfilehash: 7a274aaec4919b86f32f98e4d8278dc12748fb2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785478"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="79075-102">ICLRDataTarget::GetPointerSize (Método)</span><span class="sxs-lookup"><span data-stu-id="79075-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="79075-103">Obtiene el tamaño, en bytes, del tipo de puntero que utiliza el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="79075-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="79075-104">El servicio de acceso a datos de Common Language Runtime llama a este método.</span><span class="sxs-lookup"><span data-stu-id="79075-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79075-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79075-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79075-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="79075-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="79075-107">enuncia Un puntero a un valor entero que especifica el tamaño, en bytes, de un puntero en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="79075-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79075-108">Notas</span><span class="sxs-lookup"><span data-stu-id="79075-108">Remarks</span></span>  
 <span data-ttu-id="79075-109">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="79075-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79075-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="79075-110">Requirements</span></span>  
 <span data-ttu-id="79075-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79075-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79075-112">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="79075-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="79075-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79075-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79075-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79075-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79075-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="79075-115">See also</span></span>

- [<span data-ttu-id="79075-116">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79075-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
