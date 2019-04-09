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
ms.openlocfilehash: b0dc76a2732bf9c1e4f3a26fa2d045bfbcd837ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181095"
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="ec80d-103">Función QualifierSet_Get</span><span class="sxs-lookup"><span data-stu-id="ec80d-103">QualifierSet_Get function</span></span>
<span data-ttu-id="ec80d-104">Obtiene el calificador con nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="ec80d-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ec80d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec80d-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="ec80d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec80d-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="ec80d-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="ec80d-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="ec80d-108">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="ec80d-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="ec80d-109">[in] El nombre del calificador cuyo valor se solicita.</span><span class="sxs-lookup"><span data-stu-id="ec80d-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="ec80d-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="ec80d-110">[in] Reserved.</span></span> <span data-ttu-id="ec80d-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="ec80d-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="ec80d-112">[out] Cuando se realiza correctamente, el tipo correcto y el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="ec80d-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="ec80d-113">Si se produce un error en la función, el `VARIANT` apunta `pVal` no se modifica.</span><span class="sxs-lookup"><span data-stu-id="ec80d-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="ec80d-114">Si este parámetro es `null`, se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="ec80d-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="ec80d-115">[out] Un puntero a un valor largo que recibe los bits de tipo de calificador para el calificador solicitado.</span><span class="sxs-lookup"><span data-stu-id="ec80d-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="ec80d-116">Si no se desea obtener información de tipo, este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="ec80d-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="ec80d-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec80d-117">Return value</span></span>

<span data-ttu-id="ec80d-118">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="ec80d-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ec80d-119">Constante</span><span class="sxs-lookup"><span data-stu-id="ec80d-119">Constant</span></span>  |<span data-ttu-id="ec80d-120">Valor</span><span class="sxs-lookup"><span data-stu-id="ec80d-120">Value</span></span>  |<span data-ttu-id="ec80d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec80d-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ec80d-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ec80d-122">0x80041008</span></span> | <span data-ttu-id="ec80d-123">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="ec80d-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ec80d-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ec80d-124">0x80041002</span></span> | <span data-ttu-id="ec80d-125">El calificador especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="ec80d-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ec80d-126">0</span><span class="sxs-lookup"><span data-stu-id="ec80d-126">0</span></span> | <span data-ttu-id="ec80d-127">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="ec80d-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ec80d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec80d-128">Remarks</span></span>

<span data-ttu-id="ec80d-129">Esta función contiene una llamada a la [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) método.</span><span class="sxs-lookup"><span data-stu-id="ec80d-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ec80d-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec80d-130">Requirements</span></span>  
 <span data-ttu-id="ec80d-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec80d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec80d-132">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ec80d-132">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="ec80d-133">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ec80d-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ec80d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec80d-134">See also</span></span>

- [<span data-ttu-id="ec80d-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="ec80d-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
