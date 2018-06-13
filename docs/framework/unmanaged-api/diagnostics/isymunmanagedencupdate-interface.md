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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05cbe098b73dd817546dd72f0fc98ad548f75386
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425423"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="6c8cf-102">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8cf-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="6c8cf-103">Proporciona funciones para la característica Editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c8cf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6c8cf-104">Methods</span></span>  
  
|<span data-ttu-id="6c8cf-105">Método</span><span class="sxs-lookup"><span data-stu-id="6c8cf-105">Method</span></span>|<span data-ttu-id="6c8cf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c8cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c8cf-107">GetLocalVariableCount (método)</span><span class="sxs-lookup"><span data-stu-id="6c8cf-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="6c8cf-108">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="6c8cf-109">GetLocalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="6c8cf-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="6c8cf-110">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="6c8cf-111">InitializeForEnc (método)</span><span class="sxs-lookup"><span data-stu-id="6c8cf-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="6c8cf-112">Permite a los límites del método que debe calcularse antes de la primera llamada a la [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="6c8cf-113">UpdateMethodLines (método)</span><span class="sxs-lookup"><span data-stu-id="6c8cf-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="6c8cf-114">Permite actualizar la información de línea para un método que no se han recopilado, pero cuyos líneas se han movido por separado.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="6c8cf-115">Se permite un carácter delta para cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="6c8cf-116">UpdateSymbolStore2 (método)</span><span class="sxs-lookup"><span data-stu-id="6c8cf-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="6c8cf-117">Permite a un compilador omitir las funciones que no se han modificado desde el flujo de programa (PDB) de la base de datos, siempre que la información de línea cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="6c8cf-118">La información de línea correcta puede determinarse con la antigua información de línea PDB y un carácter delta para todas las líneas de la función.</span><span class="sxs-lookup"><span data-stu-id="6c8cf-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c8cf-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c8cf-119">Requirements</span></span>  
 <span data-ttu-id="6c8cf-120">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6c8cf-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c8cf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c8cf-121">See Also</span></span>  
 [<span data-ttu-id="6c8cf-122">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="6c8cf-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
