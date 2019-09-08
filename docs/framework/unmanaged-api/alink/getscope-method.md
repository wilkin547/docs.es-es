---
title: Método GetScope
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
ms.openlocfilehash: b3a0e42e9ffb99896bdd09dbbab65eafb40cafff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777210"
---
# <a name="getscope-method"></a><span data-ttu-id="a467a-102">Método GetScope</span><span class="sxs-lookup"><span data-stu-id="a467a-102">GetScope Method</span></span>
<span data-ttu-id="a467a-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="a467a-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a467a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a467a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a467a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a467a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a467a-106">IDENTIFICADOR único del ensamblado en el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="a467a-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a467a-107">IDENTIFICADOR único del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="a467a-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="a467a-108">Ámbito de base cero que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="a467a-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="a467a-109">Recibe la interfaz de [interfaz IMetaDataImport](../metadata/imetadataimport-interface.md) para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a467a-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a467a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a467a-110">Return Value</span></span>  
 <span data-ttu-id="a467a-111">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="a467a-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a467a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a467a-112">Requirements</span></span>  
 <span data-ttu-id="a467a-113">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="a467a-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a467a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a467a-114">See also</span></span>

- [<span data-ttu-id="a467a-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a467a-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a467a-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a467a-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a467a-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a467a-117">ALink API</span></span>](index.md)
