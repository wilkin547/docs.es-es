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
ms.openlocfilehash: aa4fe2185ead7edfa47d4194799c930193e04076
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614531"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="0061c-102">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0061c-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="0061c-103">Proporciona funciones para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="0061c-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0061c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0061c-104">Methods</span></span>  
  
|<span data-ttu-id="0061c-105">Método</span><span class="sxs-lookup"><span data-stu-id="0061c-105">Method</span></span>|<span data-ttu-id="0061c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0061c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0061c-107">Método GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="0061c-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="0061c-108">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="0061c-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="0061c-109">Método GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="0061c-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="0061c-110">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="0061c-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="0061c-111">Método InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="0061c-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="0061c-112">Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0061c-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="0061c-113">Método UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="0061c-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="0061c-114">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado.</span><span class="sxs-lookup"><span data-stu-id="0061c-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="0061c-115">Se permite una diferencia de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="0061c-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="0061c-116">Método UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="0061c-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="0061c-117">Permite a un compilador omitir las funciones que no se han modificado desde la secuencia de la base de datos de programa (PDB), siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="0061c-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="0061c-118">La información de línea correcta se puede determinar con la información de línea de PDB antigua y una diferencia para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="0061c-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0061c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0061c-119">Requirements</span></span>  
 <span data-ttu-id="0061c-120">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0061c-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0061c-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0061c-121">See also</span></span>

- [<span data-ttu-id="0061c-122">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0061c-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
