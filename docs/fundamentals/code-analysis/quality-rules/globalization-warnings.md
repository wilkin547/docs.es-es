---
title: Reglas de globalización (análisis de código)
description: Más información sobre las reglas de globalización de reglas de análisis de código
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.globalizationrules
helpviewer_keywords:
- rules, globalization
- globalization rules
- globalization [Visual Studio], rules
- managed code analysis rules, globalization rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 83ecc52c5e20e074c6c1aed68204a574494f42d5
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96594337"
---
# <a name="globalization-rules"></a>Reglas de globalización

Las reglas de globalización admiten aplicaciones y bibliotecas de uso internacional.

## <a name="in-this-section"></a>En esta sección

|Regla|Descripción|
|----------|-----------------|
|[CA1303: No pasar literales como parámetros localizados](ca1303.md)|Un método visible externamente pasa un literal de cadena como un parámetro a un constructor o método .NET, y esa cadena debe ser localizable.|
|[CA1304: Especificar CultureInfo](ca1304.md)|Un método o constructor llama a un miembro que tiene una sobrecarga que acepta un parámetro System.Globalization.CultureInfo, y el método o constructor no llama a la sobrecarga que toma el parámetro CultureInfo. Si no se proporciona un objeto CultureInfo o System.IFormatProvider, el valor predeterminado proporcionado por el miembro sobrecargado podría no surtir el efecto deseado en todas las configuraciones regionales.|
|[CA1305: Especificar IFormatProvider](ca1305.md)|Un método o constructor llama a uno o más miembros que tienen sobrecargas que aceptan un parámetro System.IFormatProvider, y el método o constructor no llama a la sobrecarga que toma el parámetro IFormatProvider. Si no se proporciona un objeto System.Globalization.CultureInfo o IFormatProvider, el valor predeterminado proporcionado por el miembro sobrecargado podría no surtir el efecto deseado en todas las configuraciones regionales.|
|[CA1307: Especificar StringComparison para mayor claridad](ca1307.md)|Una operación de comparación de cadenas utiliza una sobrecarga de método que no establece un parámetro StringComparison.|
|[CA1308: Normalizar cadenas en mayúsculas](ca1308.md)|Las cadenas se deberían normalizar para que se escriban en letras mayúsculas. Hay un grupo pequeño de caracteres que no pueden realizar un viaje de ida y vuelta cuando se pasan a minúsculas.|
|[CA1309: Utilizar StringComparison ordinal](ca1309.md)|Una operación no lingüística de comparación de cadenas no establece el parámetro StringComparison en Ordinal ni en OrdinalIgnoreCase. Si se establece explícitamente el parámetro en StringComparison.Ordinal o StringComparison.OrdinalIgnoreCase, el código será más rápido y ganará en precisión y confiabilidad.|
|[CA1310: Especificar StringComparison para mayor corrección](ca1310.md)|Una operación de comparación de cadenas utiliza una sobrecarga de método que no establece un parámetro StringComparison y utiliza de forma predeterminada la comparación de cadenas específica de la referencia cultural.|
|[CA2101: especificar el cálculo de referencias para argumentos de cadena P/Invoke](ca2101.md)|Un miembro de invocación de plataforma permite llamadores de confianza parcial, tiene un parámetro de cadena y no serializa explícitamente la cadena. Esto puede producir una vulnerabilidad de seguridad.|
