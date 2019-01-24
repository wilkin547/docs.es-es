---
title: Función GetCurrentApartmentType (referencia de API no administrada)
description: La función GetCurrentApartmentType recupera el tipo de contenedor en el que se está ejecutando el llamador.
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
ms.openlocfilehash: 8a999dc1850a41612f8896ff9a7ed96cd8c3a2fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509140"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="a6e4d-103">Función GetCurrentApartmentType</span><span class="sxs-lookup"><span data-stu-id="a6e4d-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="a6e4d-104">Recupera el tipo de contenedor en el que se está ejecutando el llamador.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-104">Retrieves the type of apartment in which the caller is executing.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a6e4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6e4d-105">Syntax</span></span>  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a><span data-ttu-id="a6e4d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6e4d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a6e4d-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a6e4d-108">[in] Un puntero a un [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instancia.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="a6e4d-109">[out] Un puntero a un [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) valor de enumeración que indica el apartamento del llamador.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-109">[out] A pointer to an [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="a6e4d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a6e4d-110">Return value</span></span>


|<span data-ttu-id="a6e4d-111">Constante</span><span class="sxs-lookup"><span data-stu-id="a6e4d-111">Constant</span></span>  |<span data-ttu-id="a6e4d-112">Valor</span><span class="sxs-lookup"><span data-stu-id="a6e4d-112">Value</span></span>  |<span data-ttu-id="a6e4d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6e4d-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="a6e4d-114">0</span><span class="sxs-lookup"><span data-stu-id="a6e4d-114">0</span></span> | <span data-ttu-id="a6e4d-115">La función que se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="a6e4d-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="a6e4d-116">0x80000008</span></span> | <span data-ttu-id="a6e4d-117">El llamador no se está ejecutando en un apartamento.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="a6e4d-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6e4d-118">Remarks</span></span>

<span data-ttu-id="a6e4d-119">Esta función contiene una llamada a la [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) método.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6e4d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6e4d-120">Requirements</span></span>  
 <span data-ttu-id="a6e4d-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e4d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e4d-122">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a6e4d-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a6e4d-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e4d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e4d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6e4d-124">See also</span></span>
- [<span data-ttu-id="a6e4d-125">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="a6e4d-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
