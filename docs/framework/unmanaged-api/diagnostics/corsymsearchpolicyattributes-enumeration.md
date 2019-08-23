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
ms.openlocfilehash: 7188c516d3d0a5192251697ec743e9d41f8d9072
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913739"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="29e12-102">CorSymSearchPolicyAttributes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="29e12-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="29e12-103">Especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="29e12-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="29e12-104">Estas constantes las usan los métodos [isymunmanagedbinder2 (:: getreaderforfile2 (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) y [Isymunmanagedbinder3 (:: getreaderfromcallback (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="29e12-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="29e12-105">Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="29e12-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29e12-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29e12-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="29e12-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="29e12-107">Members</span></span>  
  
|<span data-ttu-id="29e12-108">Member</span><span class="sxs-lookup"><span data-stu-id="29e12-108">Member</span></span>|<span data-ttu-id="29e12-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29e12-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="29e12-110">Consulta el registro para buscar rutas de acceso de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="29e12-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="29e12-111">Obtiene acceso a un servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="29e12-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="29e12-112">Busca la ruta de acceso especificada en el directorio de depuración.</span><span class="sxs-lookup"><span data-stu-id="29e12-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="29e12-113">Busca el archivo PDB en el lugar donde está el archivo. exe.</span><span class="sxs-lookup"><span data-stu-id="29e12-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29e12-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29e12-114">Requirements</span></span>  
 <span data-ttu-id="29e12-115">**Encabezado**: CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="29e12-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e12-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="29e12-116">See also</span></span>

- [<span data-ttu-id="29e12-117">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="29e12-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
