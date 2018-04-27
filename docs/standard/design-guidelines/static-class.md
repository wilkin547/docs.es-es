---
title: Diseño de clases estáticas
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a6143b128442db1ac090f0b3680f94b1ac9a9cfc
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="static-class-design"></a><span data-ttu-id="f22bc-102">Diseño de clases estáticas</span><span class="sxs-lookup"><span data-stu-id="f22bc-102">Static Class Design</span></span>
<span data-ttu-id="f22bc-103">Una clase estática se define como una clase que contiene sólo miembros estáticos (evidentemente además de los miembros de instancia se hereda de <xref:System.Object?displayProperty=nameWithType> y posiblemente un constructor privado).</span><span class="sxs-lookup"><span data-stu-id="f22bc-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="f22bc-104">Algunos lenguajes proporcionan compatibilidad integrada para las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="f22bc-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="f22bc-105">En C# 2.0 y versiones posteriores, cuando una clase se declara como estático, lo abstracto, está sellada y ningún miembro de instancia se puede invalidar o declarado.</span><span class="sxs-lookup"><span data-stu-id="f22bc-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="f22bc-106">Las clases estáticas son una solución intermedia entre puro diseño orientado a objetos y la simplicidad.</span><span class="sxs-lookup"><span data-stu-id="f22bc-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="f22bc-107">Se suelen usar para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), los propietarios de los métodos de extensión, o la funcionalidad para el que se no justificado un contenedor completa orientada a objetos (como <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="f22bc-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="f22bc-108">**✓ HACER** usan clases estáticas con moderación.</span><span class="sxs-lookup"><span data-stu-id="f22bc-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="f22bc-109">Las clases estáticas deben utilizarse únicamente como clases auxiliares para el núcleo orientada a objetos de framework.</span><span class="sxs-lookup"><span data-stu-id="f22bc-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="f22bc-110">**X DO NOT** tratar las clases estáticas como un depósito varios.</span><span class="sxs-lookup"><span data-stu-id="f22bc-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="f22bc-111">**X DO NOT** declarar o invalidar los miembros de instancia en clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="f22bc-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="f22bc-112">**✓ HACER** declarar las clases estáticas como sellada, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="f22bc-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="f22bc-113">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="f22bc-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f22bc-114">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f22bc-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22bc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f22bc-115">See Also</span></span>  
 [<span data-ttu-id="f22bc-116">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="f22bc-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="f22bc-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f22bc-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
