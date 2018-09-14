---
title: Nombres de ensamblados y bibliotecas DLL
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97bd152cff53fb1c2edb107b6d6b34bd91ca1c49
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45516229"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="ab96d-102">Nombres de ensamblados y bibliotecas DLL</span><span class="sxs-lookup"><span data-stu-id="ab96d-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="ab96d-103">Un ensamblado es la unidad de implementación y la identidad para los programas de código administrado.</span><span class="sxs-lookup"><span data-stu-id="ab96d-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="ab96d-104">Aunque los ensamblados pueden abarcar uno o varios archivos, normalmente se asigna uno a uno con un archivo DLL de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab96d-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="ab96d-105">Por lo tanto, en esta sección se describen sola convenciones de nomenclatura de DLL, que, a continuación, se pueden asignar a las convenciones de nomenclatura del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab96d-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="ab96d-106">**✓ DO** elegir nombres para el ensamblado DLL que sugieran grandes fragmentos de funcionalidad como System.Data.</span><span class="sxs-lookup"><span data-stu-id="ab96d-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="ab96d-107">No tienen nombres de ensamblado y el archivo DLL que se corresponden con los espacios de nombres, pero es razonable seguir el espacio de nombres al asignar nombres a los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ab96d-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="ab96d-108">Una buena regla general es el nombre del archivo DLL según el prefijo común de los espacios de nombres del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab96d-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="ab96d-109">Por ejemplo, un ensamblado con dos espacios de nombres, `MyCompany.MyTechnology.FirstFeature` y `MyCompany.MyTechnology.SecondFeature`, se podría llamar `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="ab96d-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="ab96d-110">**✓ CONSIDER** nomenclatura DLL según el modelo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab96d-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="ab96d-111">donde `<Component>` contiene uno o más cláusulas separados por puntos.</span><span class="sxs-lookup"><span data-stu-id="ab96d-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="ab96d-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ab96d-112">For example:</span></span>  
  
 <span data-ttu-id="ab96d-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="ab96d-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="ab96d-114">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="ab96d-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ab96d-115">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="ab96d-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab96d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab96d-116">See also</span></span>

- [<span data-ttu-id="ab96d-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ab96d-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="ab96d-118">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ab96d-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
