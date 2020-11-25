---
title: ICLRDataTarget::SetTLSValue (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: d2eaab1f42eb04d8e9727220a08842ca75a2eadf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723693"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="b21c9-102">ICLRDataTarget::SetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="b21c9-102">ICLRDataTarget::SetTLSValue Method</span></span>

<span data-ttu-id="b21c9-103">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="b21c9-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="b21c9-104">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="b21c9-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b21c9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b21c9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b21c9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b21c9-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="b21c9-107">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="b21c9-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="b21c9-108">de Índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="b21c9-108">[in] The index of the location.</span></span> <span data-ttu-id="b21c9-109">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="b21c9-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="b21c9-110">de `CLRDATA_ADDRESS` Valor que especifica el valor que se va a colocar en la ubicación TLS determinada.</span><span class="sxs-lookup"><span data-stu-id="b21c9-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b21c9-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b21c9-111">Remarks</span></span>  

 <span data-ttu-id="b21c9-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="b21c9-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b21c9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b21c9-113">Requirements</span></span>  

 <span data-ttu-id="b21c9-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b21c9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b21c9-115">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="b21c9-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b21c9-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b21c9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b21c9-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b21c9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b21c9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b21c9-118">See also</span></span>

- [<span data-ttu-id="b21c9-119">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b21c9-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
