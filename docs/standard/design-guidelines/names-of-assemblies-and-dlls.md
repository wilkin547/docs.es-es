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
ms.openlocfilehash: c6cf175472d68e99598dd56e170bee3d37ae3c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570437"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="422f6-102">Nombres de ensamblados y bibliotecas DLL</span><span class="sxs-lookup"><span data-stu-id="422f6-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="422f6-103">Un ensamblado es la unidad de implementación e identidad de los programas de código administrado.</span><span class="sxs-lookup"><span data-stu-id="422f6-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="422f6-104">Aunque los ensamblados pueden abarcar uno o más archivos, normalmente un ensamblado se asigna uno a uno con un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="422f6-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="422f6-105">Por lo tanto, en esta sección se describen sola convenciones de nomenclatura de archivos DLL, que, a continuación, se pueden asignar a las convenciones de nomenclatura ensamblado.</span><span class="sxs-lookup"><span data-stu-id="422f6-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="422f6-106">**✓ HACER** elegir nombres para el ensamblado DLL que sugieran grandes fragmentos de funcionalidad como System.Data.</span><span class="sxs-lookup"><span data-stu-id="422f6-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="422f6-107">Nombres de ensamblado y el archivo DLL no tienen que corresponder con espacios de nombres, pero es razonable seguir el nombre de espacio de nombres al asignar nombres a los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="422f6-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="422f6-108">Una buena regla general es el nombre de la DLL basada en el prefijo común de los espacios de nombres incluidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="422f6-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="422f6-109">Por ejemplo, un ensamblado con dos espacios de nombres, `MyCompany.MyTechnology.FirstFeature` y `MyCompany.MyTechnology.SecondFeature`, se podría llamar `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="422f6-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="422f6-110">**Considere la posibilidad de ✓** nomenclatura DLL según el modelo siguiente:</span><span class="sxs-lookup"><span data-stu-id="422f6-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="422f6-111">donde `<Component>` contiene una o más cláusulas separados por puntos.</span><span class="sxs-lookup"><span data-stu-id="422f6-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="422f6-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="422f6-112">For example:</span></span>  
  
 <span data-ttu-id="422f6-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="422f6-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="422f6-114">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="422f6-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="422f6-115">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="422f6-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422f6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="422f6-116">See Also</span></span>  
 [<span data-ttu-id="422f6-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="422f6-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="422f6-118">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="422f6-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
