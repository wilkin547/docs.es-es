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
ms.openlocfilehash: 5e3c2ecd1bdd5c1181223c7500eb7473e20fa5d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731350"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="91173-102">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91173-102">ISymUnmanagedENCUpdate Interface</span></span>

<span data-ttu-id="91173-103">Proporciona funciones para la característica editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="91173-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91173-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="91173-104">Methods</span></span>  
  
|<span data-ttu-id="91173-105">Método</span><span class="sxs-lookup"><span data-stu-id="91173-105">Method</span></span>|<span data-ttu-id="91173-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="91173-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91173-107">Método GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="91173-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="91173-108">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="91173-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="91173-109">Método GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="91173-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="91173-110">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="91173-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="91173-111">Método InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="91173-111">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="91173-112">Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="91173-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="91173-113">Método UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="91173-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="91173-114">Permite actualizar la información de línea para un método que no se ha vuelto a compilar, pero cuyas líneas se han desplace por separado.</span><span class="sxs-lookup"><span data-stu-id="91173-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="91173-115">Se permite una diferencia de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="91173-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="91173-116">Método UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="91173-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="91173-117">Permite a un compilador omitir las funciones que no se han modificado desde la secuencia de la base de datos de programa (PDB), siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="91173-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="91173-118">La información de línea correcta se puede determinar con la información de línea de PDB antigua y una diferencia para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="91173-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91173-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91173-119">Requirements</span></span>  

 <span data-ttu-id="91173-120">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="91173-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91173-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91173-121">See also</span></span>

- [<span data-ttu-id="91173-122">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="91173-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
