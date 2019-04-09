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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73645265821d5854776e412f8eb0f33b36db00d1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130499"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="bef23-102">ICLRDataTarget::GetPointerSize (Método)</span><span class="sxs-lookup"><span data-stu-id="bef23-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="bef23-103">Obtiene el tamaño, en bytes, del tipo de puntero que usa el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="bef23-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="bef23-104">Los servicios de acceso de datos de common language runtime llama a este método.</span><span class="sxs-lookup"><span data-stu-id="bef23-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bef23-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bef23-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bef23-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bef23-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="bef23-107">[out] Un puntero a un valor entero que especifica el tamaño, en bytes, de un puntero en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="bef23-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bef23-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bef23-108">Remarks</span></span>  
 <span data-ttu-id="bef23-109">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="bef23-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bef23-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bef23-110">Requirements</span></span>  
 <span data-ttu-id="bef23-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bef23-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bef23-112">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bef23-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bef23-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bef23-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bef23-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bef23-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bef23-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bef23-115">See also</span></span>

- [<span data-ttu-id="bef23-116">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bef23-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
