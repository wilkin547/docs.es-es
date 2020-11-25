---
title: IMetaDataImport::GetNativeCallConvFromSig (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
ms.openlocfilehash: d44ad493a786aaa35150515b7c254965490bd714
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701710"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="0fae6-102">IMetaDataImport::GetNativeCallConvFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="0fae6-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>

<span data-ttu-id="0fae6-103">Obtiene la convención de llamada nativa del método representado por el puntero de firma especificado.</span><span class="sxs-lookup"><span data-stu-id="0fae6-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fae6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fae6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fae6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fae6-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="0fae6-106">de Puntero a la firma de metadatos del método para el que se va a devolver la Convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="0fae6-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="0fae6-107">de Tamaño en bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="0fae6-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="0fae6-108">enuncia Puntero a la Convención de llamada nativa.</span><span class="sxs-lookup"><span data-stu-id="0fae6-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fae6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fae6-109">Requirements</span></span>  

 <span data-ttu-id="0fae6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fae6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fae6-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0fae6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fae6-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0fae6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0fae6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fae6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fae6-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fae6-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="0fae6-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fae6-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0fae6-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fae6-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
