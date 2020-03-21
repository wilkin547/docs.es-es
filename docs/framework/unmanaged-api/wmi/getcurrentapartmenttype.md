---
title: Función GetCurrentApartmentType (Referencia de API no administrada)
description: La función GetCurrentApartmentType recupera el tipo de apartamento en el que se ejecuta el autor de la llamada.
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
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176830"
---
# <a name="getcurrentapartmenttype-function"></a><span data-ttu-id="f3201-103">Función GetCurrentApartmentType</span><span class="sxs-lookup"><span data-stu-id="f3201-103">GetCurrentApartmentType function</span></span>
<span data-ttu-id="f3201-104">Recupera el tipo de contenedor en el que se está ejecutando el llamador.</span><span class="sxs-lookup"><span data-stu-id="f3201-104">Retrieves the type of apartment in which the caller is executing.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f3201-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3201-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a><span data-ttu-id="f3201-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3201-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f3201-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="f3201-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f3201-108">[en] Un puntero a un [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instancia.</span><span class="sxs-lookup"><span data-stu-id="f3201-108">[in] A pointer to an [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instance.</span></span>

`aptType`  
<span data-ttu-id="f3201-109">[fuera] Puntero a un valor de enumeración [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) que indica el apartamento del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f3201-109">[out] A pointer to an [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) enumeration value that indicates the caller's apartment.</span></span>

## <a name="return-value"></a><span data-ttu-id="f3201-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f3201-110">Return value</span></span>

|<span data-ttu-id="f3201-111">Constante</span><span class="sxs-lookup"><span data-stu-id="f3201-111">Constant</span></span>  |<span data-ttu-id="f3201-112">Value</span><span class="sxs-lookup"><span data-stu-id="f3201-112">Value</span></span>  |<span data-ttu-id="f3201-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3201-113">Description</span></span>  |
|---------|---------|---------|
| `S_OK` | <span data-ttu-id="f3201-114">0</span><span class="sxs-lookup"><span data-stu-id="f3201-114">0</span></span> | <span data-ttu-id="f3201-115">La función se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3201-115">The function completed successfully.</span></span> |
| `E_FAIL` | <span data-ttu-id="f3201-116">0x80000008</span><span class="sxs-lookup"><span data-stu-id="f3201-116">0x80000008</span></span> | <span data-ttu-id="f3201-117">El autor de la llamada no se está ejecutando en un apartamento.</span><span class="sxs-lookup"><span data-stu-id="f3201-117">The caller is not executing in an apartment.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f3201-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3201-118">Remarks</span></span>

<span data-ttu-id="f3201-119">Esta función ajusta una llamada a la [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) método.</span><span class="sxs-lookup"><span data-stu-id="f3201-119">This function wraps a call to the [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f3201-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3201-120">Requirements</span></span>  
 <span data-ttu-id="f3201-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3201-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3201-122">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f3201-122">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f3201-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f3201-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3201-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3201-124">See also</span></span>

- [<span data-ttu-id="f3201-125">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="f3201-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
