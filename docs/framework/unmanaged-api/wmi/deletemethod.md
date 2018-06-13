---
title: Función DeleteMethod (referencia de API no administrada)
description: La función DeleteMethod elimina el método especificado de una definición de clase CIM.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd862910d0c9bb0274158c2c516211cef598a553
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457813"
---
# <a name="deletemethod-function"></a><span data-ttu-id="b914c-103">DeleteMethod (función)</span><span class="sxs-lookup"><span data-stu-id="b914c-103">DeleteMethod function</span></span>
<span data-ttu-id="b914c-104">Elimina el método especificado de una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="b914c-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b914c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b914c-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="b914c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b914c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b914c-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b914c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b914c-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="b914c-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="b914c-109">[in] El nombre del método que se va a quitar de la tabla de la clase.</span><span class="sxs-lookup"><span data-stu-id="b914c-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="b914c-110">`wszName` debe ser un puntero a un válido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="b914c-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b914c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b914c-111">Return value</span></span>

<span data-ttu-id="b914c-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b914c-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b914c-113">Constante</span><span class="sxs-lookup"><span data-stu-id="b914c-113">Constant</span></span>  |<span data-ttu-id="b914c-114">Valor</span><span class="sxs-lookup"><span data-stu-id="b914c-114">Value</span></span>  |<span data-ttu-id="b914c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b914c-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b914c-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b914c-116">0x80041002</span></span> | <span data-ttu-id="b914c-117">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="b914c-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b914c-118">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="b914c-118">0x80041006</span></span> | <span data-ttu-id="b914c-119">No hay memoria suficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b914c-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b914c-120">0</span><span class="sxs-lookup"><span data-stu-id="b914c-120">0</span></span> | <span data-ttu-id="b914c-121">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="b914c-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b914c-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b914c-122">Remarks</span></span>

<span data-ttu-id="b914c-123">Esta función contiene una llamada a la [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="b914c-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b914c-124">No se admite la eliminación de método para [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) punteros que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="b914c-124">Method deletion is not supported for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="b914c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b914c-125">Requirements</span></span>  
 <span data-ttu-id="b914c-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b914c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b914c-127">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b914c-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b914c-128">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b914c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b914c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b914c-129">See also</span></span>  
[<span data-ttu-id="b914c-130">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b914c-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
