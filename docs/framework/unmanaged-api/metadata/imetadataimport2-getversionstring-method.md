---
description: 'Más información sobre: IMetaDataImport2:: GetVersionString ((método)'
title: IMetaDataImport2::GetVersionString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 6f7e296607dc3167936c69d52a8baae4f5555b88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688564"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="429f6-103">IMetaDataImport2::GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="429f6-103">IMetaDataImport2::GetVersionString Method</span></span>

<span data-ttu-id="429f6-104">Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="429f6-104">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="429f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="429f6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="429f6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="429f6-106">Parameters</span></span>  

 `pwzBuf`  
 <span data-ttu-id="429f6-107">enuncia Matriz para almacenar la cadena que especifica la versión.</span><span class="sxs-lookup"><span data-stu-id="429f6-107">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="429f6-108">de Tamaño, en caracteres anchos, de la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="429f6-108">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="429f6-109">enuncia El número de caracteres anchos, incluido un terminador nulo, devuelto en la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="429f6-109">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="429f6-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="429f6-110">Remarks</span></span>  

 <span data-ttu-id="429f6-111">El `GetVersionString` método obtiene la versión integrada del ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="429f6-111">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="429f6-112">Si el ámbito no se ha guardado nunca, no tendrá una versión integrada y se devolverá una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="429f6-112">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="429f6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="429f6-113">Requirements</span></span>  

 <span data-ttu-id="429f6-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="429f6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="429f6-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="429f6-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="429f6-116">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="429f6-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="429f6-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="429f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="429f6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="429f6-118">See also</span></span>

- [<span data-ttu-id="429f6-119">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="429f6-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="429f6-120">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="429f6-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
