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
# <a name="naming-parameters"></a>Asignar nombres a parámetros

Aparte de la razón obvia de legibilidad, es importante seguir las directrices para los nombres de parámetro, ya que los parámetros se muestran en la documentación y en el diseñador cuando las herramientas de diseño visual proporcionan la funcionalidad de exploración de clases y de IntelliSense.

 ✔️ usar alterne en los nombres de parámetro.

 ✔️ utilizan nombres de parámetro descriptivos.

 ✔️ considere la posibilidad de usar nombres basados en el significado de un parámetro en lugar del tipo del parámetro.

### <a name="naming-operator-overload-parameters"></a>Parámetros de sobrecarga del operador de nomenclatura

 ✔️ usar `left` y `right` para los nombres de parámetro de sobrecarga del operador binario si no hay ningún significado para los parámetros.

 ✔️ usar `value` para los nombres de parámetro de sobrecarga del operador unario si no hay ningún significado para los parámetros.

 ✔️ CONSIDERE nombres descriptivos para los parámetros de sobrecarga de operadores si esto agrega un valor significativo.

 ❌ No utilice abreviaturas ni índices numéricos para los nombres de parámetro de sobrecarga del operador.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de nomenclatura](naming-guidelines.md)
