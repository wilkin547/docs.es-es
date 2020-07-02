---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620635"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>Los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador (un objeto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>). Al intentar serializar un catálogo de MEF se inicia una excepción.

#### <a name="suggestion"></a>Sugerencia

Ya no se puede usar MEF para crear un serializador.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
