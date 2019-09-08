---
title: ExportType (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 455f71c5b576d1b57db591dab2a3e59f8a5eed67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777290"
---
# <a name="exporttype-method"></a><span data-ttu-id="0fadf-102">ExportType (Método)</span><span class="sxs-lookup"><span data-stu-id="0fadf-102">ExportType Method</span></span>
<span data-ttu-id="0fadf-103">Especifica que un tipo es exportable.</span><span class="sxs-lookup"><span data-stu-id="0fadf-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fadf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fadf-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fadf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fadf-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0fadf-106">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="0fadf-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0fadf-107">Token de archivo o ID. de ensamblado del archivo que define el tipo exportable.</span><span class="sxs-lookup"><span data-stu-id="0fadf-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="0fadf-108">Token del tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="0fadf-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="0fadf-109">Nombre completo del tipo que se va a convertir en exportable.</span><span class="sxs-lookup"><span data-stu-id="0fadf-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0fadf-110">`ComType`marcas como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="0fadf-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="0fadf-111">Este parámetro se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="0fadf-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="0fadf-112">Recibe el token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="0fadf-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fadf-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0fadf-113">Return Value</span></span>  
 <span data-ttu-id="0fadf-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0fadf-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fadf-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fadf-115">Requirements</span></span>  
 <span data-ttu-id="0fadf-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="0fadf-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fadf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fadf-117">See also</span></span>

- [<span data-ttu-id="0fadf-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fadf-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0fadf-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fadf-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0fadf-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="0fadf-120">ALink API</span></span>](index.md)
