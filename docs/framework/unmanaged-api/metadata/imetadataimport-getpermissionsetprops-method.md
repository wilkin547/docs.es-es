---
title: IMetaDataImport::GetPermissionSetProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 54c75156c32e5b40aa933ef6530b2cc33edf7de4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490996"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="c6ca7-102">IMetaDataImport::GetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="c6ca7-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="c6ca7-103">Obtiene los metadatos asociados al <xref:System.Security.PermissionSet?displayProperty=nameWithType> representado por el token de permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="c6ca7-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ca7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6ca7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6ca7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6ca7-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="c6ca7-106">de Token de metadatos de permiso que representa el conjunto de permisos para el que se van a obtener las propiedades de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c6ca7-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="c6ca7-107">enuncia Puntero al conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="c6ca7-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="c6ca7-108">enuncia Puntero a la firma de metadatos binarios del conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="c6ca7-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="c6ca7-109">enuncia Tamaño en bytes de `ppvPermission` .</span><span class="sxs-lookup"><span data-stu-id="c6ca7-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ca7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6ca7-110">Requirements</span></span>  
 <span data-ttu-id="c6ca7-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ca7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ca7-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c6ca7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6ca7-113">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c6ca7-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6ca7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6ca7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ca7-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c6ca7-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="c6ca7-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6ca7-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c6ca7-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6ca7-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
