---
ms.openlocfilehash: fbc39b6e1cc19f6c2846caaabb9a8a721494b4e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67856925"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Permitir Unicode en URI similares a los recursos compartidos UNC

|   |   |
|---|---|
|Detalles|En <xref:System.Uri?displayProperty=fullName>, la construcción de un URI que contenga un nombre de recurso compartido UNC y caracteres Unicode ya no dará como resultado un URI con el estado interno no válido. El comportamiento solo cambiará cuando se cumpla todo lo siguiente:<ul><li>El URI tiene el esquema <code>file:</code> y va seguido de cuatro o más barras diagonales.</li><li>El nombre de host comienza con un carácter de subrayado u otro símbolo no reservado.</li><li>El URI contiene caracteres Unicode.</li></ul>|
|Sugerencia|Las aplicaciones que trabajan con URI que contienen Unicode de forma coherente podrían haber usado este comportamiento para no permitir referencias a recursos compartidos UNC. En su lugar, esas aplicaciones deben usar <xref:System.Uri.IsUnc>.|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
