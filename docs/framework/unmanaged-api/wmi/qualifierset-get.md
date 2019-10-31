---
title: Función QualifierSet_Get (referencia de la API no administrada)
description: La función QualifierSet_Get obtiene un calificador con nombre.
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
ms.openlocfilehash: dc09cd30c43647fa00cccc1dc00da4f8de367e84
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127273"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="5f700-103">QualifierSet_Get función)</span><span class="sxs-lookup"><span data-stu-id="5f700-103">QualifierSet_Get function</span></span>
<span data-ttu-id="5f700-104">Obtiene el calificador con nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="5f700-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5f700-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f700-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="5f700-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f700-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="5f700-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5f700-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="5f700-108">de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="5f700-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="5f700-109">de Nombre del calificador cuyo valor se solicita.</span><span class="sxs-lookup"><span data-stu-id="5f700-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="5f700-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="5f700-110">[in] Reserved.</span></span> <span data-ttu-id="5f700-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="5f700-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="5f700-112">enuncia Cuando se realiza correctamente, el tipo y el valor correctos para el calificador.</span><span class="sxs-lookup"><span data-stu-id="5f700-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="5f700-113">Si se produce un error en la función, el `VARIANT` al que apunta `pVal` no se modifica.</span><span class="sxs-lookup"><span data-stu-id="5f700-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="5f700-114">Si este parámetro es `null`, se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="5f700-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="5f700-115">enuncia Un puntero a un LONG que recibe los bits de sabor del calificador para el calificador solicitado.</span><span class="sxs-lookup"><span data-stu-id="5f700-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="5f700-116">Si no se desea información de tipo, este parámetro se puede `null`.</span><span class="sxs-lookup"><span data-stu-id="5f700-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="5f700-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f700-117">Return value</span></span>

<span data-ttu-id="5f700-118">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="5f700-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5f700-119">Constante</span><span class="sxs-lookup"><span data-stu-id="5f700-119">Constant</span></span>  |<span data-ttu-id="5f700-120">Valor</span><span class="sxs-lookup"><span data-stu-id="5f700-120">Value</span></span>  |<span data-ttu-id="5f700-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f700-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5f700-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5f700-122">0x80041008</span></span> | <span data-ttu-id="5f700-123">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="5f700-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="5f700-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5f700-124">0x80041002</span></span> | <span data-ttu-id="5f700-125">El calificador especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="5f700-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5f700-126">0</span><span class="sxs-lookup"><span data-stu-id="5f700-126">0</span></span> | <span data-ttu-id="5f700-127">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5f700-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5f700-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f700-128">Remarks</span></span>

<span data-ttu-id="5f700-129">Esta función contiene una llamada al método [IWbemQualifierSet:: get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) .</span><span class="sxs-lookup"><span data-stu-id="5f700-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f700-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f700-130">Requirements</span></span>  
 <span data-ttu-id="5f700-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f700-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f700-132">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="5f700-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5f700-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5f700-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f700-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f700-134">See also</span></span>

- [<span data-ttu-id="5f700-135">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="5f700-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
