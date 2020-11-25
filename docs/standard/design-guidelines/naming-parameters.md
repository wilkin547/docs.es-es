---
title: Asignar nombres a parámetros
description: Obtenga información sobre las directrices para la nomenclatura de parámetros. Por ejemplo, use nombres de parámetro descriptivos & la grafía Camel, & considere la posibilidad de asignar nombres en función del significado en lugar del tipo.
ms.date: 10/22/2008
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 9f03eda511c2ef0c9565d270c52fd72bf54692d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698356"
---
# <a name="naming-parameters"></a><span data-ttu-id="1b5d3-104">Asignar nombres a parámetros</span><span class="sxs-lookup"><span data-stu-id="1b5d3-104">Naming Parameters</span></span>

<span data-ttu-id="1b5d3-105">Aparte de la razón obvia de legibilidad, es importante seguir las directrices para los nombres de parámetro, ya que los parámetros se muestran en la documentación y en el diseñador cuando las herramientas de diseño visual proporcionan la funcionalidad de exploración de clases y de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-105">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>

 <span data-ttu-id="1b5d3-106">✔️ usar alterne en los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-106">✔️ DO use camelCasing in parameter names.</span></span>

 <span data-ttu-id="1b5d3-107">✔️ utilizan nombres de parámetro descriptivos.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-107">✔️ DO use descriptive parameter names.</span></span>

 <span data-ttu-id="1b5d3-108">✔️ considere la posibilidad de usar nombres basados en el significado de un parámetro en lugar del tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-108">✔️ CONSIDER using names based on a parameter’s meaning rather than the parameter’s type.</span></span>

### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="1b5d3-109">Parámetros de sobrecarga del operador de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1b5d3-109">Naming Operator Overload Parameters</span></span>

 <span data-ttu-id="1b5d3-110">✔️ usar `left` y `right` para los nombres de parámetro de sobrecarga del operador binario si no hay ningún significado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-110">✔️ DO use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="1b5d3-111">✔️ usar `value` para los nombres de parámetro de sobrecarga del operador unario si no hay ningún significado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-111">✔️ DO use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="1b5d3-112">✔️ CONSIDERE nombres descriptivos para los parámetros de sobrecarga de operadores si esto agrega un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-112">✔️ CONSIDER meaningful names for operator overload parameters if doing so adds significant value.</span></span>

 <span data-ttu-id="1b5d3-113">❌ No utilice abreviaturas ni índices numéricos para los nombres de parámetro de sobrecarga del operador.</span><span class="sxs-lookup"><span data-stu-id="1b5d3-113">❌ DO NOT use abbreviations or numeric indices for operator overload parameter names.</span></span>

 <span data-ttu-id="1b5d3-114">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="1b5d3-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1b5d3-115">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="1b5d3-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1b5d3-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b5d3-116">See also</span></span>

- [<span data-ttu-id="1b5d3-117">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="1b5d3-117">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="1b5d3-118">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1b5d3-118">Naming Guidelines</span></span>](naming-guidelines.md)
