---
description: 'Más información acerca de: interfaz ISymUnmanagedENCUpdate'
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
ms.openlocfilehash: 4527dfbba840be00cf87a80cdcef3cbde6f275df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721429"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="141d9-103">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="141d9-103">ISymUnmanagedENCUpdate Interface</span></span>

<span data-ttu-id="141d9-104">Proporciona funciones para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="141d9-104">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="141d9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="141d9-105">Methods</span></span>  
  
|<span data-ttu-id="141d9-106">Método</span><span class="sxs-lookup"><span data-stu-id="141d9-106">Method</span></span>|<span data-ttu-id="141d9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="141d9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="141d9-108">Método GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="141d9-108">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="141d9-109">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="141d9-109">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="141d9-110">Método GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="141d9-110">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="141d9-111">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="141d9-111">Gets the local variables.</span></span>|  
|[<span data-ttu-id="141d9-112">Método InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="141d9-112">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="141d9-113">Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="141d9-113">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="141d9-114">Método UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="141d9-114">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="141d9-115">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado.</span><span class="sxs-lookup"><span data-stu-id="141d9-115">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="141d9-116">Se permite una diferencia de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="141d9-116">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="141d9-117">Método UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="141d9-117">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="141d9-118">Permite a un compilador omitir las funciones que no se han modificado desde la secuencia de la base de datos de programa (PDB), siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="141d9-118">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="141d9-119">La información de línea correcta se puede determinar con la información de línea de PDB antigua y una diferencia para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="141d9-119">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="141d9-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="141d9-120">Requirements</span></span>  

 <span data-ttu-id="141d9-121">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="141d9-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141d9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="141d9-122">See also</span></span>

- [<span data-ttu-id="141d9-123">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="141d9-123">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
