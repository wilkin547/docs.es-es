---
description: 'Más información acerca de: Strongnamegetblob ((función)'
title: StrongNameGetBlob (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
ms.openlocfilehash: 72f7ce50ce6170a23e5b24b68f911ff58bebe3bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736445"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="d8b44-103">StrongNameGetBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="d8b44-103">StrongNameGetBlob Function</span></span>

<span data-ttu-id="d8b44-104">Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="d8b44-104">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="d8b44-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="d8b44-105">This function has been deprecated.</span></span> <span data-ttu-id="d8b44-106">Use el método [ICLRStrongName:: strongnamegetblob (](../hosting/iclrstrongname-strongnamegetblob-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d8b44-106">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b44-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8b44-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8b44-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8b44-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="d8b44-109">de Ruta de acceso válida al archivo ejecutable que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="d8b44-109">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="d8b44-110">de Búfer en el que se va a cargar el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="d8b44-110">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="d8b44-111">[in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="d8b44-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="d8b44-112">Después de la devolución, el tamaño real, en bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="d8b44-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8b44-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8b44-113">Return Value</span></span>  

 <span data-ttu-id="d8b44-114">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="d8b44-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8b44-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d8b44-115">Remarks</span></span>  

 <span data-ttu-id="d8b44-116">Si la `StrongNameGetBlob` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="d8b44-116">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8b44-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8b44-117">Requirements</span></span>  

 <span data-ttu-id="d8b44-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8b44-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8b44-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d8b44-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d8b44-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8b44-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8b44-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8b44-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b44-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8b44-122">See also</span></span>

- [<span data-ttu-id="d8b44-123">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="d8b44-123">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="d8b44-124">Método StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="d8b44-124">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="d8b44-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8b44-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
