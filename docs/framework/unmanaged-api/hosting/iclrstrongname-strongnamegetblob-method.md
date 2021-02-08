---
description: 'Más información sobre: ICLRStrongName:: Strongnamegetblob ((método)'
title: ICLRStrongName::StrongNameGetBlob (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 2b63ebd9c48ad18eef60f83c68fe412a4bd0d94f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799634"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="ea7c1-103">ICLRStrongName::StrongNameGetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="ea7c1-103">ICLRStrongName::StrongNameGetBlob Method</span></span>

<span data-ttu-id="ea7c1-104">Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="ea7c1-104">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7c1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea7c1-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea7c1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea7c1-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="ea7c1-107">de Ruta de acceso válida al archivo ejecutable que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="ea7c1-107">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="ea7c1-108">de Búfer en el que se va a cargar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="ea7c1-108">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="ea7c1-109">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="ea7c1-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="ea7c1-110">Después de la devolución, el tamaño real, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="ea7c1-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea7c1-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ea7c1-111">Return Value</span></span>  

 <span data-ttu-id="ea7c1-112">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="ea7c1-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea7c1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea7c1-113">Requirements</span></span>  

 <span data-ttu-id="ea7c1-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea7c1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea7c1-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ea7c1-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ea7c1-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea7c1-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea7c1-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea7c1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7c1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea7c1-118">See also</span></span>

- [<span data-ttu-id="ea7c1-119">Método StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="ea7c1-119">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="ea7c1-120">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea7c1-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
