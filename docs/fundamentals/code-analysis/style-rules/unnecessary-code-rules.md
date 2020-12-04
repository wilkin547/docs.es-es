---
title: Reglas de código innecesario
description: Más información sobre las reglas de código innecesarias del análisis de código
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "96594641"
---
# <a name="unnecessary-code-rules"></a>Reglas de código innecesario

Las reglas de código innecesarias identifican distintas partes de la base de código que no son necesarias y se pueden refactorizar o quitar. La presencia de código innecesario indica uno de los siguientes problemas:

- Legibilidad: código que está desduciendo innecesariamente la legibilidad. Por ejemplo, [IDE0001](ide0001.md) marca las calificaciones innecesarias de nombre de tipo.
- Mantenimiento: código que ya no se utiliza después de la refactorización y que se mantiene innecesariamente. Por ejemplo, [IDE0051](ide0051.md) marca los campos, propiedades, eventos y métodos privados sin usar.
- Rendimiento: cálculo innecesario que no tiene efectos secundarios y genera una sobrecarga de rendimiento innecesaria. Por ejemplo, [IDE0059](ide0059.md) marca las asignaciones de valores no utilizadas en las que la expresión para calcular un valor no tiene efectos secundarios.
- Funcionalidad: problema funcional en el código que hace que el código necesario se represente como redundante. Por ejemplo, [IDE0060](ide0060.md) marca los parámetros no usados en los que el método omite accidentalmente un parámetro de entrada.

Las reglas de esta sección se refieren a las siguientes reglas de código innecesario:

- [Nombre simplificado (IDE0001)](ide0001.md)
- [Simplificar el acceso a miembros (IDE0002)](ide0002.md)
- [Quitar conversión innecesaria (IDE0004)](ide0004.md)
- [Quitar importación innecesaria (IDE0005)](ide0005.md)
- [Quitar código inaccesible (IDE0035)](ide0035.md)
- [Quitar miembro privado no utilizado (IDE0051)](ide0051.md)
- [Quitar miembro privado no leído (IDE0052)](ide0052.md)
- [Quitar el valor de expresión sin usar (IDE0058)](ide0058.md)
- [Quitar la asignación de valores innecesarios (IDE0059)](ide0059.md)
- [Quitar el parámetro sin usar (IDE0060)](ide0060.md)
- [Quitar supresión innecesaria (IDE0079)](ide0079.md)
- [Quitar el operador de supresión innecesario (IDE0080) (](ide0080.md) solo C#).
- [Quitar ' ByVal ' (IDE0081)](ide0081.md) : solo Visual Basic.
- [Quitar el operador de igualdad innecesario (IDE0100)](ide0100.md)
- [Quitar descartar innecesariamente (IDE0110)](ide0110.md) : solo C#.

Algunas de estas reglas tienen opciones para configurar el comportamiento de la regla:

- [csharp_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [visual_basic_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [csharp_style_unused_value_assignment_preference (IDE0059)](ide0059.md#csharp_style_unused_value_assignment_preference)
- [visual_basic_style_unused_value_assignment_preference (IDE0059)](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [dotnet_code_quality_unused_parameters (IDE0060)](ide0060.md#dotnet_code_quality_unused_parameters)
- [dotnet_remove_unnecessary_suppression_exclusions (IDE0079)](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a>Vea también

- [Reglas del lenguaje de estilo de código](language-rules.md)
- [Referencia de reglas de estilo de código](index.md)
