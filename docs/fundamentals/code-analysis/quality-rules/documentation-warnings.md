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
# <a name="documentation-rules"></a>Reglas de documentación

Las reglas de documentación permiten escribir bibliotecas bien documentadas mediante el uso correcto de [comentarios de documentación XML](../../../csharp/codedoc.md) para API visibles externamente.

## <a name="in-this-section"></a>En esta sección

| Regla | Descripción |
| - | - |
| [CA1200: Evitar el uso de etiquetas cref con un prefijo](ca1200.md) | El atributo [CREF](../../../csharp/programming-guide/xmldoc/cref-attribute.md) de una etiqueta de documentación XML significa "referencia de código". Especifica que el texto interno de la etiqueta es un elemento de código, como un tipo, un método o una propiedad. Evite el uso de `cref` etiquetas con prefijos, ya que impide que el compilador Compruebe las referencias. También impide que el entorno de desarrollo integrado (IDE) de Visual Studio busque y actualice estas referencias de símbolos durante las refactorizaciones. |
