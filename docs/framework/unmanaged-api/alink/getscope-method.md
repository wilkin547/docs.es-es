---
title: GetScope Method1
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2746073fbc6adfd7090aa9b3cc38e46c4411744
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400190"
---
# <a name="getscope-method1"></a><span data-ttu-id="73e44-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="73e44-102">GetScope Method1</span></span>
<span data-ttu-id="73e44-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="73e44-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e44-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73e44-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73e44-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73e44-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="73e44-106">Identificador único del ensamblado que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="73e44-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="73e44-107">Identificador único del archivo que se va a importar desde.</span><span class="sxs-lookup"><span data-stu-id="73e44-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="73e44-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="73e44-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="73e44-109">Recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="73e44-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73e44-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="73e44-110">Return Value</span></span>  
 <span data-ttu-id="73e44-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="73e44-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73e44-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73e44-112">Requirements</span></span>  
 <span data-ttu-id="73e44-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="73e44-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e44-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="73e44-114">See Also</span></span>  
 [<span data-ttu-id="73e44-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73e44-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="73e44-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73e44-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="73e44-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="73e44-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
