---
title: Nombres de ensamblados y bibliotecas DLL
description: Obtenga información sobre las directrices para asignar nombres a ensamblados y bibliotecas de vínculos dinámicos (dll). Un ensamblado puede abarcar uno o varios archivos, pero normalmente se asigna uno a uno con un archivo DLL.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: 95a90ff66ffc9f2a5a3202d6877b1cc19149ff35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706533"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="25ddf-104">Nombres de ensamblados y bibliotecas DLL</span><span class="sxs-lookup"><span data-stu-id="25ddf-104">Names of Assemblies and DLLs</span></span>

<span data-ttu-id="25ddf-105">Un ensamblado es la unidad de implementación e identidad para los programas de código administrado.</span><span class="sxs-lookup"><span data-stu-id="25ddf-105">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="25ddf-106">Aunque los ensamblados pueden abarcar uno o varios archivos, normalmente un ensamblado se asigna uno a uno con un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="25ddf-106">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="25ddf-107">Por lo tanto, en esta sección solo se describen las convenciones de nomenclatura de archivos DLL, que se pueden asignar a las convenciones de nomenclatura de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="25ddf-107">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="25ddf-108">✔️ Elija nombres para los archivos dll de ensamblado que sugieran grandes fragmentos de funcionalidad, como System. Data.</span><span class="sxs-lookup"><span data-stu-id="25ddf-108">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="25ddf-109">No es necesario que los nombres de ensamblado y DLL se correspondan con los nombres de espacios de nombres, pero es razonable seguir el nombre del espacio de nombres al asignar nombres a los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="25ddf-109">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="25ddf-110">Una buena regla general es asignar un nombre a la DLL basándose en el prefijo común de los espacios de nombres contenidos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="25ddf-110">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="25ddf-111">Por ejemplo, `MyCompany.MyTechnology.FirstFeature` `MyCompany.MyTechnology.SecondFeature` se podría llamar a un ensamblado con dos espacios de nombres, y `MyCompany.MyTechnology.dll` .</span><span class="sxs-lookup"><span data-stu-id="25ddf-111">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="25ddf-112">✔️ considere la posibilidad de asignar nombres a los archivos dll según el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="25ddf-112">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="25ddf-113">donde `<Component>` contiene una o más cláusulas separadas por puntos.</span><span class="sxs-lookup"><span data-stu-id="25ddf-113">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="25ddf-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="25ddf-114">For example:</span></span>

 <span data-ttu-id="25ddf-115">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="25ddf-115">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="25ddf-116">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="25ddf-116">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="25ddf-117">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="25ddf-117">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="25ddf-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25ddf-118">See also</span></span>

- [<span data-ttu-id="25ddf-119">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="25ddf-119">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="25ddf-120">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="25ddf-120">Naming Guidelines</span></span>](naming-guidelines.md)
