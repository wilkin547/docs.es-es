---
title: Función DeleteMethod (referencia de la API no administrada)
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
ms.openlocfilehash: db360584dacf250be2f35e5e6666f8332b39a8dd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120646"
---
# <a name="deletemethod-function"></a><span data-ttu-id="46fc6-103">Función DeleteMethod</span><span class="sxs-lookup"><span data-stu-id="46fc6-103">DeleteMethod function</span></span>
<span data-ttu-id="46fc6-104">Elimina el método especificado de una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="46fc6-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="46fc6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46fc6-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="46fc6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46fc6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="46fc6-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="46fc6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="46fc6-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="46fc6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="46fc6-109">de Nombre del método que se va a quitar de la tabla de clases.</span><span class="sxs-lookup"><span data-stu-id="46fc6-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="46fc6-110">`wszName` debe ser un puntero a una `LPCWSTR`válida.</span><span class="sxs-lookup"><span data-stu-id="46fc6-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="46fc6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="46fc6-111">Return value</span></span>

<span data-ttu-id="46fc6-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="46fc6-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="46fc6-113">Constante</span><span class="sxs-lookup"><span data-stu-id="46fc6-113">Constant</span></span>  |<span data-ttu-id="46fc6-114">Valor</span><span class="sxs-lookup"><span data-stu-id="46fc6-114">Value</span></span>  |<span data-ttu-id="46fc6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="46fc6-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="46fc6-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="46fc6-116">0x80041002</span></span> | <span data-ttu-id="46fc6-117">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="46fc6-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="46fc6-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="46fc6-118">0x80041006</span></span> | <span data-ttu-id="46fc6-119">No hay suficiente memoria para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="46fc6-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="46fc6-120">0</span><span class="sxs-lookup"><span data-stu-id="46fc6-120">0</span></span> | <span data-ttu-id="46fc6-121">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="46fc6-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="46fc6-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46fc6-122">Remarks</span></span>

<span data-ttu-id="46fc6-123">Esta función contiene una llamada al método [IWbemClassObject::D eletemethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) .</span><span class="sxs-lookup"><span data-stu-id="46fc6-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="46fc6-124">No se admite la eliminación de métodos para punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que apunten a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="46fc6-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="46fc6-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46fc6-125">Requirements</span></span>  
 <span data-ttu-id="46fc6-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46fc6-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46fc6-127">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="46fc6-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="46fc6-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46fc6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46fc6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="46fc6-129">See also</span></span>

- [<span data-ttu-id="46fc6-130">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="46fc6-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
