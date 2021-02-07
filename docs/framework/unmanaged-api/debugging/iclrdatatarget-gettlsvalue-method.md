---
description: 'Más información acerca de: ICLRDataTarget:: Gettlsvalue ((método)'
title: ICLRDataTarget::GetTLSValue (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
ms.openlocfilehash: 5c0c4a462d89c2eceada4180ea532f36fc9e48b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718049"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="048fb-103">ICLRDataTarget::GetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="048fb-103">ICLRDataTarget::GetTLSValue Method</span></span>

<span data-ttu-id="048fb-104">Obtiene un valor del almacenamiento local para el subproceso (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="048fb-104">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="048fb-105">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="048fb-105">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="048fb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="048fb-106">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="048fb-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="048fb-107">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="048fb-108">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="048fb-108">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="048fb-109">de Índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="048fb-109">[in] The index of the location.</span></span> <span data-ttu-id="048fb-110">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="048fb-110">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="048fb-111">enuncia Un puntero a un `CLRDATA_ADDRESS` valor que especifica el valor devuelto desde la ubicación TLS determinada.</span><span class="sxs-lookup"><span data-stu-id="048fb-111">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="048fb-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="048fb-112">Remarks</span></span>  

 <span data-ttu-id="048fb-113">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="048fb-113">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="048fb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="048fb-114">Requirements</span></span>  

 <span data-ttu-id="048fb-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="048fb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="048fb-116">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="048fb-116">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="048fb-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="048fb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="048fb-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="048fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="048fb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="048fb-119">See also</span></span>

- [<span data-ttu-id="048fb-120">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="048fb-120">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
