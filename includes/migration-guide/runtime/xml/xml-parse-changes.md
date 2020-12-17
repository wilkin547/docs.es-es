---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009075"
---
### <a name="xml-parsing-changes"></a>Cambios de análisis en XML

| NOMBRE    | Valor   |
|:--------|:--------|
| Ámbito   | Secundaria   |
| Versión | 4.5.2   |
| Tipo    | Tiempo de ejecución |

#### <a name="details"></a>Detalles

Por motivos de seguridad, se han efectuado los cambios siguientes en las API de análisis en XML:

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> se ha establecido en 10 millones al inicializar <xref:System.Xml.XmlReaderSettings>.
- De forma predeterminada, la propiedad <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> se establece en `null`.

> [!NOTE]
> Todos los analizadores en XML usan <xref:System.Xml.XmlReaderSettings>, por lo que, aunque este cambio ayuda al caso <xref:System.Xml.XmlReader>, también afecta a otros escenarios.

#### <a name="suggestion"></a>Sugerencia

Para revertir el comportamiento a uno anterior, puede establecer un valor en el registro. Agregue un valor DWORD denominado `EnableLegacyXmlSettings` a la clave del registro `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` y establezca su valor en `1`. También puede agregar el valor del registro en el subárbol HKEY_CURRENT_USER.

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

Además, afectará a cualquier API XML que dependa de <xref:System.Xml.XmlResolver>, ya sea directa o indirectamente.

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
