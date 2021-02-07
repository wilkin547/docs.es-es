---
description: 'Más información sobre: ICeeGen (interfaz)'
title: ICeeGen (Interfaz)
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: 43e9e0696523346ffbcf0b8823a48ed2c9c359e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706817"
---
# <a name="iceegen-interface"></a><span data-ttu-id="f406c-103">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f406c-103">ICeeGen Interface</span></span>

<span data-ttu-id="f406c-104">Proporciona métodos para la compilación de código dinámico.</span><span class="sxs-lookup"><span data-stu-id="f406c-104">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="f406c-105">Esta interfaz está obsoleta y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="f406c-105">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f406c-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="f406c-106">Methods</span></span>  
  
|<span data-ttu-id="f406c-107">Método</span><span class="sxs-lookup"><span data-stu-id="f406c-107">Method</span></span>|<span data-ttu-id="f406c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f406c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f406c-109">Método AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="f406c-109">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)|<span data-ttu-id="f406c-110">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-110">Obsolete.</span></span> <span data-ttu-id="f406c-111">Agrega una instrucción. reloc al código base.</span><span class="sxs-lookup"><span data-stu-id="f406c-111">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="f406c-112">Método AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="f406c-112">AllocateMethodBuffer Method</span></span>](iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="f406c-113">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-113">Obsolete.</span></span> <span data-ttu-id="f406c-114">Crea un búfer con el tamaño especificado para un método y obtiene la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="f406c-114">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="f406c-115">Método ComputePointer</span><span class="sxs-lookup"><span data-stu-id="f406c-115">ComputePointer Method</span></span>](iceegen-computepointer-method.md)|<span data-ttu-id="f406c-116">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-116">Obsolete.</span></span> <span data-ttu-id="f406c-117">Determina el búfer para la sección de código especificada.</span><span class="sxs-lookup"><span data-stu-id="f406c-117">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="f406c-118">Método EmitString</span><span class="sxs-lookup"><span data-stu-id="f406c-118">EmitString Method</span></span>](iceegen-emitstring-method.md)|<span data-ttu-id="f406c-119">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-119">Obsolete.</span></span> <span data-ttu-id="f406c-120">Emite la cadena especificada en el código base.</span><span class="sxs-lookup"><span data-stu-id="f406c-120">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="f406c-121">Método GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="f406c-121">GenerateCeeFile Method</span></span>](iceegen-generateceefile-method.md)|<span data-ttu-id="f406c-122">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-122">Obsolete.</span></span> <span data-ttu-id="f406c-123">Genera un archivo de código base que contiene el código base cargado actualmente en este `ICeeGen` .</span><span class="sxs-lookup"><span data-stu-id="f406c-123">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="f406c-124">Método GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="f406c-124">GenerateCeeMemoryImage Method</span></span>](iceegen-generateceememoryimage-method.md)|<span data-ttu-id="f406c-125">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-125">Obsolete.</span></span> <span data-ttu-id="f406c-126">Genera una imagen en memoria para la base de código.</span><span class="sxs-lookup"><span data-stu-id="f406c-126">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="f406c-127">Método GetIlSection</span><span class="sxs-lookup"><span data-stu-id="f406c-127">GetIlSection Method</span></span>](iceegen-getilsection-method.md)|<span data-ttu-id="f406c-128">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-128">Obsolete.</span></span> <span data-ttu-id="f406c-129">Obtiene la sección de la base de código de lenguaje intermedio a la que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="f406c-129">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f406c-130">Método GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="f406c-130">GetIMapTokenIface Method</span></span>](iceegen-getimaptokeniface-method.md)|<span data-ttu-id="f406c-131">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-131">Obsolete.</span></span> <span data-ttu-id="f406c-132">Obtiene la interfaz a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="f406c-132">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="f406c-133">Método GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="f406c-133">GetMethodBuffer Method</span></span>](iceegen-getmethodbuffer-method.md)|<span data-ttu-id="f406c-134">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-134">Obsolete.</span></span> <span data-ttu-id="f406c-135">Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="f406c-135">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f406c-136">Método GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="f406c-136">GetSectionBlock Method</span></span>](iceegen-getsectionblock-method.md)|<span data-ttu-id="f406c-137">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-137">Obsolete.</span></span> <span data-ttu-id="f406c-138">Obtiene un bloque de sección del código base.</span><span class="sxs-lookup"><span data-stu-id="f406c-138">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="f406c-139">Método GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="f406c-139">GetSectionCreate Method</span></span>](iceegen-getsectioncreate-method.md)|<span data-ttu-id="f406c-140">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-140">Obsolete.</span></span> <span data-ttu-id="f406c-141">Genera y obtiene una sección de código usando el nombre y los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="f406c-141">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="f406c-142">Método GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="f406c-142">GetSectionDataLen Method</span></span>](iceegen-getsectiondatalen-method.md)|<span data-ttu-id="f406c-143">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-143">Obsolete.</span></span> <span data-ttu-id="f406c-144">Obtiene la longitud de la sección especificada.</span><span class="sxs-lookup"><span data-stu-id="f406c-144">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="f406c-145">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="f406c-145">GetString Method</span></span>](iceegen-getstring-method.md)|<span data-ttu-id="f406c-146">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-146">Obsolete.</span></span> <span data-ttu-id="f406c-147">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="f406c-147">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f406c-148">Método GetStringSection</span><span class="sxs-lookup"><span data-stu-id="f406c-148">GetStringSection Method</span></span>](iceegen-getstringsection-method.md)|<span data-ttu-id="f406c-149">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-149">Obsolete.</span></span> <span data-ttu-id="f406c-150">Obtiene una representación de cadena de la sección de código a la que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="f406c-150">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f406c-151">Método TruncateSection</span><span class="sxs-lookup"><span data-stu-id="f406c-151">TruncateSection Method</span></span>](iceegen-truncatesection-method.md)|<span data-ttu-id="f406c-152">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f406c-152">Obsolete.</span></span> <span data-ttu-id="f406c-153">Trunca la sección de código especificada según la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="f406c-153">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f406c-154">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f406c-154">Requirements</span></span>  

 <span data-ttu-id="f406c-155">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f406c-155">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f406c-156">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f406c-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f406c-157">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f406c-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f406c-158">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f406c-158">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f406c-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="f406c-159">See also</span></span>

- [<span data-ttu-id="f406c-160">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="f406c-160">Metadata Interfaces</span></span>](metadata-interfaces.md)
