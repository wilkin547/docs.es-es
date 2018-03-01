---
title: ISymUnmanagedENCUpdate (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f68d000824779fcffb90ec031b86b50e8c80eccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="b5f55-102">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5f55-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="b5f55-103">Proporciona funciones para la característica Editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="b5f55-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5f55-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b5f55-104">Methods</span></span>  
  
|<span data-ttu-id="b5f55-105">Método</span><span class="sxs-lookup"><span data-stu-id="b5f55-105">Method</span></span>|<span data-ttu-id="b5f55-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5f55-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b5f55-107">GetLocalVariableCount (método)</span><span class="sxs-lookup"><span data-stu-id="b5f55-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="b5f55-108">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="b5f55-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="b5f55-109">GetLocalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="b5f55-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="b5f55-110">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="b5f55-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="b5f55-111">InitializeForEnc (método)</span><span class="sxs-lookup"><span data-stu-id="b5f55-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="b5f55-112">Permite a los límites del método que debe calcularse antes de la primera llamada a la [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b5f55-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="b5f55-113">UpdateMethodLines (método)</span><span class="sxs-lookup"><span data-stu-id="b5f55-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="b5f55-114">Permite actualizar la información de línea para un método que no se han recopilado, pero cuyos líneas se han movido por separado.</span><span class="sxs-lookup"><span data-stu-id="b5f55-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="b5f55-115">Se permite un carácter delta para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="b5f55-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="b5f55-116">UpdateSymbolStore2 (método)</span><span class="sxs-lookup"><span data-stu-id="b5f55-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="b5f55-117">Permite a un compilador omitir las funciones que no se han modificado desde el flujo de programa (PDB) de la base de datos, siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="b5f55-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="b5f55-118">La información de línea correcta puede determinarse con la antigua información de línea PDB y un carácter delta para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="b5f55-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5f55-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5f55-119">Requirements</span></span>  
 <span data-ttu-id="b5f55-120">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b5f55-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f55-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5f55-121">See Also</span></span>  
 [<span data-ttu-id="b5f55-122">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b5f55-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
