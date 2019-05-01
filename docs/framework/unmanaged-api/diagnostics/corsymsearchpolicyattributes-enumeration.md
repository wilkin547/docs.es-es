---
title: CorSymSearchPolicyAttributes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a9b0f085820bac12638c0310ab23b2eafacb23b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986510"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="47bdf-102">CorSymSearchPolicyAttributes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="47bdf-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="47bdf-103">Especifica la directiva que se usará al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="47bdf-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="47bdf-104">Estas constantes se utilizan por el [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) y [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="47bdf-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47bdf-105">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="47bdf-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47bdf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47bdf-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="47bdf-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="47bdf-107">Members</span></span>  
  
|<span data-ttu-id="47bdf-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="47bdf-108">Member</span></span>|<span data-ttu-id="47bdf-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="47bdf-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="47bdf-110">Consulta el registro para las rutas de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="47bdf-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="47bdf-111">Tiene acceso a un servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="47bdf-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="47bdf-112">Busca la ruta de acceso especificada en el directorio de depuración.</span><span class="sxs-lookup"><span data-stu-id="47bdf-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="47bdf-113">Busca el archivo PDB en el lugar donde está el archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="47bdf-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47bdf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47bdf-114">Requirements</span></span>  
 <span data-ttu-id="47bdf-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="47bdf-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47bdf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="47bdf-116">See also</span></span>

- [<span data-ttu-id="47bdf-117">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="47bdf-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
