---
title: ISymUnmanagedENCUpdate (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: f3305a7bb003fc50f772f1100f8a17d385e4d5fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449005"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="9adb7-102">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9adb7-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="9adb7-103">Proporciona funciones para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="9adb7-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9adb7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9adb7-104">Methods</span></span>  
  
|<span data-ttu-id="9adb7-105">Método</span><span class="sxs-lookup"><span data-stu-id="9adb7-105">Method</span></span>|<span data-ttu-id="9adb7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9adb7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9adb7-107">GetLocalVariableCount (método)</span><span class="sxs-lookup"><span data-stu-id="9adb7-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="9adb7-108">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="9adb7-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="9adb7-109">GetLocalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="9adb7-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="9adb7-110">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="9adb7-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="9adb7-111">InitializeForEnc (método)</span><span class="sxs-lookup"><span data-stu-id="9adb7-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="9adb7-112">Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9adb7-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="9adb7-113">UpdateMethodLines (método)</span><span class="sxs-lookup"><span data-stu-id="9adb7-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="9adb7-114">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado.</span><span class="sxs-lookup"><span data-stu-id="9adb7-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="9adb7-115">Se permite una diferencia de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="9adb7-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="9adb7-116">UpdateSymbolStore2 (método)</span><span class="sxs-lookup"><span data-stu-id="9adb7-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="9adb7-117">Permite a un compilador omitir las funciones que no se han modificado desde la secuencia de la base de datos de programa (PDB), siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="9adb7-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="9adb7-118">La información de línea correcta se puede determinar con la información de línea de PDB antigua y una diferencia para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="9adb7-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9adb7-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9adb7-119">Requirements</span></span>  
 <span data-ttu-id="9adb7-120">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9adb7-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9adb7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9adb7-121">See also</span></span>

- [<span data-ttu-id="9adb7-122">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="9adb7-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
