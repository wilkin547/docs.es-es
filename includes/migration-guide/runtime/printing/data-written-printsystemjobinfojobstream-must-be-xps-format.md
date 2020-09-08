---
ms.openlocfilehash: 19be8a7755d9b238ab6507eaa73319bddf39faa3
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496256"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a>Los datos escritos en PrintSystemJobInfo.JobStream deben estar en formato XPS

#### <a name="details"></a>Detalles

La propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> expone la secuencia de un trabajo de impresión. El usuario puede enviar datos sin formato a los componentes de impresión del sistema operativo subyacente si escribe en esta secuencia. A partir de .NET Framework 4.5 en Windows 8 y versiones posteriores del sistema operativo Windows, los datos que se escriben en esta secuencia deben estar en formato XPS como una secuencia de paquete.

#### <a name="suggestion"></a>Sugerencia

Para mostrar contenido de impresión, puede realizar una de las acciones siguientes:<ul><li>Utilice la clase <xref:System.Windows.Xps.XpsDocumentWriter> para mostrar contenido de impresión. Esta es la alternativa recomendada.</li><li>Asegúrese de que los datos enviados a la secuencia que devuelve la propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> están en formato XPS como una secuencia de paquete.</li></ul>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Printing.PrintSystemJobInfo.JobStream`

-->
