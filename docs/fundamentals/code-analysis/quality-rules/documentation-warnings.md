---
title: Reglas de documentación (análisis de código)
description: Más información sobre las reglas de documentación de reglas de análisis de código
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation rules
- managed code analysis rules, documentation rules
- warnings, documentation
author: mavasani
ms.author: mavasani
ms.openlocfilehash: 29d1734eec29bd00d456b4b00c48c2e8ef223441
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592666"
---
# <a name="documentation-rules"></a><span data-ttu-id="d41a5-103">Reglas de documentación</span><span class="sxs-lookup"><span data-stu-id="d41a5-103">Documentation rules</span></span>

<span data-ttu-id="d41a5-104">Las reglas de documentación permiten escribir bibliotecas bien documentadas mediante el uso correcto de [comentarios de documentación XML](../../../csharp/codedoc.md) para API visibles externamente.</span><span class="sxs-lookup"><span data-stu-id="d41a5-104">Documentation rules support writing well-documented libraries through the correct use of [XML documentation comments](../../../csharp/codedoc.md) for externally visible APIs.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d41a5-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d41a5-105">In this section</span></span>

| <span data-ttu-id="d41a5-106">Regla</span><span class="sxs-lookup"><span data-stu-id="d41a5-106">Rule</span></span> | <span data-ttu-id="d41a5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d41a5-107">Description</span></span> |
| - | - |
| [<span data-ttu-id="d41a5-108">CA1200: Evitar el uso de etiquetas cref con un prefijo</span><span class="sxs-lookup"><span data-stu-id="d41a5-108">CA1200: Avoid using cref tags with a prefix</span></span>](ca1200.md) | <span data-ttu-id="d41a5-109">El atributo [CREF](../../../csharp/programming-guide/xmldoc/cref-attribute.md) de una etiqueta de documentación XML significa "referencia de código".</span><span class="sxs-lookup"><span data-stu-id="d41a5-109">The [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) attribute in an XML documentation tag means "code reference".</span></span> <span data-ttu-id="d41a5-110">Especifica que el texto interno de la etiqueta es un elemento de código, como un tipo, un método o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="d41a5-110">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="d41a5-111">Evite el uso de `cref` etiquetas con prefijos, ya que impide que el compilador Compruebe las referencias.</span><span class="sxs-lookup"><span data-stu-id="d41a5-111">Avoid using `cref` tags with prefixes, because it prevents the compiler from verifying references.</span></span> <span data-ttu-id="d41a5-112">También impide que el entorno de desarrollo integrado (IDE) de Visual Studio busque y actualice estas referencias de símbolos durante las refactorizaciones.</span><span class="sxs-lookup"><span data-stu-id="d41a5-112">It also prevents the Visual Studio integrated development environment (IDE) from finding and updating these symbol references during refactorings.</span></span> |
