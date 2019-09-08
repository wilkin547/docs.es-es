---
title: IAssemblyCacheItem::CreateStream (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af7dc4e1694b66fc4a5ce37e515c71e9fa3db49
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796731"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="9dc75-102">IAssemblyCacheItem::CreateStream (Método)</span><span class="sxs-lookup"><span data-stu-id="9dc75-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="9dc75-103">Crea una secuencia con el nombre y el formato especificados.</span><span class="sxs-lookup"><span data-stu-id="9dc75-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="9dc75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dc75-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="9dc75-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9dc75-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="9dc75-106">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="9dc75-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="9dc75-107">de Nombre del flujo que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="9dc75-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="9dc75-108">de Formato del archivo que se va a transmitir por secuencias.</span><span class="sxs-lookup"><span data-stu-id="9dc75-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="9dc75-109">de Marcas específicas del formato definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="9dc75-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="9dc75-110">enuncia Puntero a la dirección de la instancia de [IStream](/windows/desktop/api/objidl/nn-objidl-istream) devuelta.</span><span class="sxs-lookup"><span data-stu-id="9dc75-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="9dc75-111">[in, Optional] Tamaño máximo de la secuencia a `ppIStream`la que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="9dc75-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="9dc75-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dc75-112">Requirements</span></span>

<span data-ttu-id="9dc75-113">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dc75-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="9dc75-114">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9dc75-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="9dc75-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dc75-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9dc75-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dc75-116">See also</span></span>

- [<span data-ttu-id="9dc75-117">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dc75-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
