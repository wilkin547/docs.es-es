---
title: "CorSymSearchPolicyAttributes (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymSearchPolicyAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymSearchPolicyAttributes
helpviewer_keywords: CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 016378de8d4ba4b6f16f7e7b91b6427f73c9687d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="58db9-102">CorSymSearchPolicyAttributes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="58db9-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="58db9-103">Especifica la directiva que se utilizará al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="58db9-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="58db9-104">Estas constantes se utilizan por la [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) y [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="58db9-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58db9-105">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="58db9-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58db9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58db9-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="58db9-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="58db9-107">Members</span></span>  
  
|<span data-ttu-id="58db9-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="58db9-108">Member</span></span>|<span data-ttu-id="58db9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="58db9-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="58db9-110">Consulta el registro de las rutas de acceso de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="58db9-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="58db9-111">Tiene acceso a un servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="58db9-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="58db9-112">Busca la ruta de acceso especificada en el directorio de depuración.</span><span class="sxs-lookup"><span data-stu-id="58db9-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="58db9-113">Busca el archivo PDB en el lugar donde está el archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="58db9-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58db9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58db9-114">Requirements</span></span>  
 <span data-ttu-id="58db9-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="58db9-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58db9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="58db9-116">See Also</span></span>  
 [<span data-ttu-id="58db9-117">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="58db9-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
