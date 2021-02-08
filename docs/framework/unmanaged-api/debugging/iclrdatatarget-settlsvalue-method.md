---
description: 'Más información acerca de: ICLRDataTarget:: Settlsvalue ((método)'
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
ms.openlocfilehash: 2432cd66f604575e35f171c98a0fb313c5ccd94e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785692"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="689a4-103">ICLRDataTarget::SetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="689a4-103">ICLRDataTarget::SetTLSValue Method</span></span>

<span data-ttu-id="689a4-104">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="689a4-104">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="689a4-105">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="689a4-105">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="689a4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="689a4-106">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="689a4-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="689a4-107">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="689a4-108">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="689a4-108">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="689a4-109">de Índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="689a4-109">[in] The index of the location.</span></span> <span data-ttu-id="689a4-110">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="689a4-110">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="689a4-111">de `CLRDATA_ADDRESS` Valor que especifica el valor que se va a colocar en la ubicación TLS determinada.</span><span class="sxs-lookup"><span data-stu-id="689a4-111">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="689a4-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="689a4-112">Remarks</span></span>  

 <span data-ttu-id="689a4-113">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="689a4-113">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="689a4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="689a4-114">Requirements</span></span>  

 <span data-ttu-id="689a4-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="689a4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="689a4-116">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="689a4-116">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="689a4-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="689a4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="689a4-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="689a4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="689a4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="689a4-119">See also</span></span>

- [<span data-ttu-id="689a4-120">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="689a4-120">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
