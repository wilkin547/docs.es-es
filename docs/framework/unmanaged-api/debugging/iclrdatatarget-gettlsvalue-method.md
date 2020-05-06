---
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
ms.openlocfilehash: 141dc8632812ab4a2ce82864cde56337025baa28
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860585"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="f2751-102">ICLRDataTarget::GetTLSValue (Método)</span><span class="sxs-lookup"><span data-stu-id="f2751-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="f2751-103">Obtiene un valor del almacenamiento local para el subproceso (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="f2751-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="f2751-104">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="f2751-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2751-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2751-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2751-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2751-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="f2751-107">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="f2751-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="f2751-108">de Índice de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="f2751-108">[in] The index of the location.</span></span> <span data-ttu-id="f2751-109">Este valor debe ser un índice válido en el almacén local del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="f2751-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="f2751-110">enuncia Un puntero a un `CLRDATA_ADDRESS` valor que especifica el valor devuelto desde la ubicación TLS determinada.</span><span class="sxs-lookup"><span data-stu-id="f2751-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2751-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2751-111">Remarks</span></span>  
 <span data-ttu-id="f2751-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="f2751-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2751-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2751-113">Requirements</span></span>  
 <span data-ttu-id="f2751-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2751-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2751-115">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="f2751-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f2751-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2751-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2751-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2751-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2751-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2751-118">See also</span></span>

- [<span data-ttu-id="f2751-119">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2751-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
