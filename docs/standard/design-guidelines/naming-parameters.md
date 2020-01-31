---
title: Asignar nombres a parámetros
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: ebe2e2db4b109057bf576d4e18cfe511c657707e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743831"
---
# <a name="naming-parameters"></a><span data-ttu-id="fb79b-102">Asignar nombres a parámetros</span><span class="sxs-lookup"><span data-stu-id="fb79b-102">Naming Parameters</span></span>
<span data-ttu-id="fb79b-103">Aparte de la razón obvia de legibilidad, es importante seguir las directrices para los nombres de parámetro, ya que los parámetros se muestran en la documentación y en el diseñador cuando las herramientas de diseño visual proporcionan la funcionalidad de exploración de clases y de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="fb79b-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>

 <span data-ttu-id="fb79b-104">✔️ usar alterne en los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="fb79b-104">✔️ DO use camelCasing in parameter names.</span></span>

 <span data-ttu-id="fb79b-105">✔️ utilizan nombres de parámetro descriptivos.</span><span class="sxs-lookup"><span data-stu-id="fb79b-105">✔️ DO use descriptive parameter names.</span></span>

 <span data-ttu-id="fb79b-106">✔️ considere la posibilidad de usar nombres basados en el significado de un parámetro en lugar del tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="fb79b-106">✔️ CONSIDER using names based on a parameter’s meaning rather than the parameter’s type.</span></span>

### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="fb79b-107">Parámetros de sobrecarga del operador de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fb79b-107">Naming Operator Overload Parameters</span></span>
 <span data-ttu-id="fb79b-108">✔️ usar `left` y `right` para los nombres de parámetro de sobrecarga del operador binario si no hay ningún significado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="fb79b-108">✔️ DO use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="fb79b-109">✔️ usar `value` para los nombres de parámetro de sobrecarga del operador unario si no hay ningún significado para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="fb79b-109">✔️ DO use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>

 <span data-ttu-id="fb79b-110">✔️ CONSIDERE nombres descriptivos para los parámetros de sobrecarga de operadores si esto agrega un valor significativo.</span><span class="sxs-lookup"><span data-stu-id="fb79b-110">✔️ CONSIDER meaningful names for operator overload parameters if doing so adds significant value.</span></span>

 <span data-ttu-id="fb79b-111">❌ no usan abreviaturas ni índices numéricos para los nombres de parámetro de sobrecarga del operador.</span><span class="sxs-lookup"><span data-stu-id="fb79b-111">❌ DO NOT use abbreviations or numeric indices for operator overload parameter names.</span></span>

 <span data-ttu-id="fb79b-112">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="fb79b-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="fb79b-113">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="fb79b-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="fb79b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb79b-114">See also</span></span>

- [<span data-ttu-id="fb79b-115">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fb79b-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="fb79b-116">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="fb79b-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
