---
title: Función QualifierSet_Get (referencia de API no administrada)
description: La función QualifierSet_Get Obtiene un calificador con nombre.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1bc57ab45a0452d9e3a50f0ab2de786ad73204a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458652"
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="d5c8d-103">QualifierSet_Get (función)</span><span class="sxs-lookup"><span data-stu-id="d5c8d-103">QualifierSet_Get function</span></span>
<span data-ttu-id="d5c8d-104">Obtiene el calificador con nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d5c8d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5c8d-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d5c8d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5c8d-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="d5c8d-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="d5c8d-108">[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="d5c8d-109">[in] El nombre del calificador cuyo valor se solicita.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="d5c8d-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-110">[in] Reserved.</span></span> <span data-ttu-id="d5c8d-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="d5c8d-112">[out] Cuando se realiza correctamente, el tipo correcto y el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="d5c8d-113">Si se produce un error en la función, el `VARIANT` que señala `pVal` no se modifica.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="d5c8d-114">Si este parámetro es `null`, se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="d5c8d-115">[out] Un puntero a un valor largo que recibe los bits del tipo de calificador para el calificador solicitado.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="d5c8d-116">Si no se desea obtener información de tipo, este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="d5c8d-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5c8d-117">Return value</span></span>

<span data-ttu-id="d5c8d-118">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="d5c8d-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d5c8d-119">Constante</span><span class="sxs-lookup"><span data-stu-id="d5c8d-119">Constant</span></span>  |<span data-ttu-id="d5c8d-120">Valor</span><span class="sxs-lookup"><span data-stu-id="d5c8d-120">Value</span></span>  |<span data-ttu-id="d5c8d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5c8d-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d5c8d-122">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="d5c8d-122">0x80041008</span></span> | <span data-ttu-id="d5c8d-123">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="d5c8d-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="d5c8d-124">0x80041002</span></span> | <span data-ttu-id="d5c8d-125">El calificador especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d5c8d-126">0</span><span class="sxs-lookup"><span data-stu-id="d5c8d-126">0</span></span> | <span data-ttu-id="d5c8d-127">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d5c8d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5c8d-128">Remarks</span></span>

<span data-ttu-id="d5c8d-129">Esta función contiene una llamada a la [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="d5c8d-129">This function wraps a call to the [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d5c8d-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5c8d-130">Requirements</span></span>  
 <span data-ttu-id="d5c8d-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5c8d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5c8d-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d5c8d-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d5c8d-133">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c8d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c8d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5c8d-134">See also</span></span>  
[<span data-ttu-id="d5c8d-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="d5c8d-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
