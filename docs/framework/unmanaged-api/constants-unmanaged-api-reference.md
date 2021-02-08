---
description: 'Más información sobre: constantes (referencia de la API no administrada)'
title: Constantes (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
ms.openlocfilehash: 39641b4a98f921a3e8a004f536e0683cb81ab74e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772801"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="76736-103">Constantes (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="76736-103">Constants (Unmanaged API Reference)</span></span>

<span data-ttu-id="76736-104">En este tema se describen las constantes de tipo de lenguaje, proveedor de lenguaje y tipo de documento que se definen en CorSym. idl.</span><span class="sxs-lookup"><span data-stu-id="76736-104">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="76736-105">Constantes de tipo de lenguaje</span><span class="sxs-lookup"><span data-stu-id="76736-105">Language Type Constants</span></span>  

 <span data-ttu-id="76736-106">En la tabla siguiente se muestran las constantes de tipo de lenguaje, que representan los GUID que identifican los lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="76736-106">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="76736-107">Símbolo</span><span class="sxs-lookup"><span data-stu-id="76736-107">Symbol</span></span>|<span data-ttu-id="76736-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="76736-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="76736-109">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="76736-109">CorSym_LanguageType_C</span></span>|<span data-ttu-id="76736-110">Indica el lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="76736-110">Indicates the C language.</span></span>|  
|<span data-ttu-id="76736-111">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="76736-111">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="76736-112">Indica el lenguaje C++.</span><span class="sxs-lookup"><span data-stu-id="76736-112">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="76736-113">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="76736-113">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="76736-114">Indica el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="76736-114">Indicates the C# language.</span></span>|  
|<span data-ttu-id="76736-115">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="76736-115">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="76736-116">Indica el lenguaje básico.</span><span class="sxs-lookup"><span data-stu-id="76736-116">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="76736-117">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="76736-117">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="76736-118">Indica el lenguaje Java.</span><span class="sxs-lookup"><span data-stu-id="76736-118">Indicates the Java language.</span></span>|  
|<span data-ttu-id="76736-119">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="76736-119">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="76736-120">Indica el lenguaje COBOL.</span><span class="sxs-lookup"><span data-stu-id="76736-120">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="76736-121">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="76736-121">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="76736-122">Indica el lenguaje Pascal.</span><span class="sxs-lookup"><span data-stu-id="76736-122">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="76736-123">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="76736-123">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="76736-124">Indica el código de ensamblado del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="76736-124">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="76736-125">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="76736-125">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="76736-126">Indica el lenguaje JScript.</span><span class="sxs-lookup"><span data-stu-id="76736-126">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="76736-127">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="76736-127">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="76736-128">Indica el lenguaje SMC.</span><span class="sxs-lookup"><span data-stu-id="76736-128">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="76736-129">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="76736-129">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="76736-130">Indica el lenguaje C++ habilitado para el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76736-130">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="76736-131">Constantes de proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="76736-131">Language Vendor Constants</span></span>  

 <span data-ttu-id="76736-132">En la tabla siguiente se muestran las constantes de proveedor de lenguaje, que representan los GUID que identifican a los proveedores de lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="76736-132">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="76736-133">Símbolo</span><span class="sxs-lookup"><span data-stu-id="76736-133">Symbol</span></span>|<span data-ttu-id="76736-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="76736-134">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="76736-135">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="76736-135">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="76736-136">Indica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76736-136">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="76736-137">Constantes de tipo de documento</span><span class="sxs-lookup"><span data-stu-id="76736-137">Document Type Constants</span></span>  

 <span data-ttu-id="76736-138">En la tabla siguiente se muestran las constantes de tipo de documento, que representan los GUID que identifican los tipos de documento.</span><span class="sxs-lookup"><span data-stu-id="76736-138">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="76736-139">Símbolo</span><span class="sxs-lookup"><span data-stu-id="76736-139">Symbol</span></span>|<span data-ttu-id="76736-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="76736-140">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="76736-141">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="76736-141">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="76736-142">Indica un documento de texto.</span><span class="sxs-lookup"><span data-stu-id="76736-142">Indicates a text document.</span></span>|  
|<span data-ttu-id="76736-143">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="76736-143">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="76736-144">Indica un documento que no es de texto.</span><span class="sxs-lookup"><span data-stu-id="76736-144">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76736-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76736-145">See also</span></span>

- [<span data-ttu-id="76736-146">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="76736-146">Unmanaged API Reference</span></span>](index.md)
