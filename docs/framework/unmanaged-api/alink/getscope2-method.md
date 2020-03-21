---
title: GetScope2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: 40df78cdf99c2e0f53be9664f3f5c6386b6c6f93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179398"
---
# <a name="getscope2-method"></a><span data-ttu-id="cec77-102">GetScope2 (Método)</span><span class="sxs-lookup"><span data-stu-id="cec77-102">GetScope2 Method</span></span>
<span data-ttu-id="cec77-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="cec77-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cec77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="cec77-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cec77-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cec77-106">ID del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="cec77-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cec77-107">ID del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="cec77-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="cec77-108">Alcance de base cero que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="cec77-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="cec77-109">Recibe el puntero a [Interfaz IMetaDataImport2](../metadata/imetadataimport2-interface.md) interfaz para el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="cec77-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cec77-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cec77-110">Return Value</span></span>  
 <span data-ttu-id="cec77-111">Devuelve S_OK si el método se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="cec77-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cec77-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cec77-112">Requirements</span></span>  
 <span data-ttu-id="cec77-113">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="cec77-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec77-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cec77-114">See also</span></span>

- [<span data-ttu-id="cec77-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cec77-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cec77-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cec77-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cec77-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="cec77-117">ALink API</span></span>](index.md)
