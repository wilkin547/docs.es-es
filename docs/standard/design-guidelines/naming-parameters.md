---
title: "Asignar nombres a parámetros"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a10fa8835bfbcf826f8a3bb9318966e0dc603864
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="naming-parameters"></a><span data-ttu-id="dfd3f-102">Asignar nombres a parámetros</span><span class="sxs-lookup"><span data-stu-id="dfd3f-102">Naming Parameters</span></span>
<span data-ttu-id="dfd3f-103">Más allá de la razón obvia de legibilidad, es importante seguir las directrices para los nombres de parámetro porque los parámetros se muestran en la documentación y en el diseñador cuando las herramientas de diseño visual proporcionan Intellisense y la funcionalidad de exploración de clase.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="dfd3f-104">**✓ HACER** utilice seguir el estilo Camel en los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="dfd3f-105">**✓ HACER** usar nombres de parámetros descriptivos.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="dfd3f-106">**✓ Considere la posibilidad de** con nombres basados en el significado de un parámetro en lugar de en el tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="dfd3f-107">Nombres de parámetros de sobrecarga de operador</span><span class="sxs-lookup"><span data-stu-id="dfd3f-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="dfd3f-108">**✓ HACER** usar `left` y `right` para nombres de parámetros de sobrecarga de operador binario si no hay ningún significado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="dfd3f-109">**✓ HACER** usar `value` para unario sobrecarga de operador nombres de parámetro si no hay ningún significado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="dfd3f-110">**✓ Considere la posibilidad de** nombres significativos para el operador de sobrecarga parámetros si ello aumentaría valor significativo.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="dfd3f-111">**X DO NOT** use abreviaturas o índices numéricos para el operador de sobrecarga nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="dfd3f-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="dfd3f-112">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="dfd3f-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dfd3f-113">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="dfd3f-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd3f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfd3f-114">See Also</span></span>  
 [<span data-ttu-id="dfd3f-115">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dfd3f-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="dfd3f-116">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="dfd3f-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
