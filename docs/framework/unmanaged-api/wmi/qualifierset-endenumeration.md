---
title: Función QualifierSet_EndEnumeration (referencia de la API no administrada)
description: La función QualifierSet_EndEnumeration finaliza una enumeración.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 82627fa416f71e123ed2c03bae4584e4433310eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127290"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="3c924-103">QualifierSet_EndEnumeration función)</span><span class="sxs-lookup"><span data-stu-id="3c924-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="3c924-104">Finaliza la enumeración iniciada con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3c924-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3c924-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c924-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="3c924-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c924-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3c924-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3c924-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="3c924-108">de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="3c924-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="3c924-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c924-109">Return value</span></span>

<span data-ttu-id="3c924-110">El siguiente valor devuelto por esta función se define en el archivo de encabezado *WbemCli. h* , o bien se puede definir como una constante en el código:</span><span class="sxs-lookup"><span data-stu-id="3c924-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="3c924-111">Constante</span><span class="sxs-lookup"><span data-stu-id="3c924-111">Constant</span></span>  |<span data-ttu-id="3c924-112">Valor</span><span class="sxs-lookup"><span data-stu-id="3c924-112">Value</span></span>  |<span data-ttu-id="3c924-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c924-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3c924-114">0</span><span class="sxs-lookup"><span data-stu-id="3c924-114">0</span></span> | <span data-ttu-id="3c924-115">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3c924-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3c924-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c924-116">Remarks</span></span>

<span data-ttu-id="3c924-117">Esta función contiene una llamada al método [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .</span><span class="sxs-lookup"><span data-stu-id="3c924-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="3c924-118">Se recomienda esta llamada, pero no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="3c924-118">This call is recommended, but not required.</span></span> <span data-ttu-id="3c924-119">Libera inmediatamente los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="3c924-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c924-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c924-120">Requirements</span></span>  

<span data-ttu-id="3c924-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c924-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="3c924-122">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="3c924-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="3c924-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3c924-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c924-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c924-124">See also</span></span>

- [<span data-ttu-id="3c924-125">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="3c924-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
