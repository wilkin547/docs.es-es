---
title: Función GetCurrentApartmentType (referencia de la API no administrada)
description: La función GetCurrentApartmentType recupera el tipo de apartamento en el que se está ejecutando el autor de la llamada.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff64be47802a46979818ab54cc3efb4112dd05e0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798618"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="18b56-103">GetCurrentApartmentType función)</span><span class="sxs-lookup"><span data-stu-id="18b56-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="18b56-104">Recupera el tipo de contenedor en el que se está ejecutando el llamador.</span><span class="sxs-lookup"><span data-stu-id="18b56-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="18b56-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18b56-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="18b56-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="18b56-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="18b56-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="18b56-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="18b56-108">de Puntero a una instancia de [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) .</span><span class="sxs-lookup"><span data-stu-id="18b56-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="18b56-109">enuncia Un puntero a un valor de enumeración [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) que indica el apartamento del llamador.</span><span class="sxs-lookup"><span data-stu-id="18b56-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="18b56-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="18b56-110">Return value</span></span>

|<span data-ttu-id="18b56-111">Constante</span><span class="sxs-lookup"><span data-stu-id="18b56-111">Constant</span></span>  |<span data-ttu-id="18b56-112">Valor</span><span class="sxs-lookup"><span data-stu-id="18b56-112">Value</span></span>  |<span data-ttu-id="18b56-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="18b56-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="18b56-114">0</span><span class="sxs-lookup"><span data-stu-id="18b56-114">0</span></span> | <span data-ttu-id="18b56-115">La función se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="18b56-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="18b56-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="18b56-116">0x80000008</span></span> | <span data-ttu-id="18b56-117">El autor de la llamada no se está ejecutando en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="18b56-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="18b56-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18b56-118">Remarks</span></span>

<span data-ttu-id="18b56-119">Esta función contiene una llamada al método [IComThreadingInfo:: GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="18b56-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="18b56-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18b56-120">Requirements</span></span>  
 <span data-ttu-id="18b56-121">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18b56-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18b56-122">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="18b56-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="18b56-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18b56-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b56-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="18b56-124">See also</span></span>

- [<span data-ttu-id="18b56-125">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="18b56-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
