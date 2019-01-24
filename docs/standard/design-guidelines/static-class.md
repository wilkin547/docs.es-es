---
title: Diseño de clases estáticas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: KrzysztofCwalina
ms.openlocfilehash: d0a2f11b53f50f2ec2f301f7b88df65e1cd7b811
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617387"
---
# <a name="static-class-design"></a><span data-ttu-id="ca839-102">Diseño de clases estáticas</span><span class="sxs-lookup"><span data-stu-id="ca839-102">Static Class Design</span></span>
<span data-ttu-id="ca839-103">Se define una clase estática como una clase que contiene sólo miembros estáticos (por supuesto además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y, posiblemente, un constructor privado).</span><span class="sxs-lookup"><span data-stu-id="ca839-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="ca839-104">Algunos lenguajes ofrecen compatibilidad integrada para las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="ca839-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="ca839-105">En C# 2.0 y versiones posteriores, cuando una clase se declara como estática, está sellada y abstracta y se puede invalidar o declarado ningún miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="ca839-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="ca839-106">Las clases estáticas son un compromiso entre el diseño orientado a objetos puro y simplicidad.</span><span class="sxs-lookup"><span data-stu-id="ca839-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="ca839-107">Se suelen usar para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), los propietarios de los métodos de extensión o la funcionalidad para el que se no fundamentado un contenedor completa orientada a objetos (como <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="ca839-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="ca839-108">**✓ DO** usan clases estáticas con moderación.</span><span class="sxs-lookup"><span data-stu-id="ca839-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="ca839-109">Las clases estáticas deben usarse solo como clases auxiliares para las principales orientada a objetos de framework.</span><span class="sxs-lookup"><span data-stu-id="ca839-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="ca839-110">**X DO NOT** tratar las clases estáticas como un depósito varios.</span><span class="sxs-lookup"><span data-stu-id="ca839-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="ca839-111">**X DO NOT** declarar o invalidar los miembros de instancia en clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="ca839-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="ca839-112">**✓ DO** declarar las clases estáticas como sellada, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="ca839-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="ca839-113">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="ca839-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ca839-114">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="ca839-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca839-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca839-115">See also</span></span>

- [<span data-ttu-id="ca839-116">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="ca839-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="ca839-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ca839-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
