---
ms.openlocfilehash: 74f00821f2304664729faa8de2f0163c6611f513
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805059"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a>Los datos escritos en PrintSystemJobInfo.JobStream deben estar en formato XPS

|   |   |
|---|---|
|Detalles|La propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> expone la secuencia de un trabajo de impresión. El usuario puede enviar datos sin formato a los componentes de impresión del sistema operativo subyacente si escribe en esta secuencia. A partir de .NET Framework 4.5 en Windows 8 y versiones posteriores del sistema operativo Windows, los datos que se escriben en esta secuencia deben estar en formato XPS como una secuencia de paquete.|
|Sugerencia|Para mostrar contenido de impresión, puede realizar una de las acciones siguientes:<ul><li>Utilice la clase <xref:System.Windows.Xps.XpsDocumentWriter> para mostrar contenido de impresión. Esta es la alternativa recomendada.</li><li>Asegúrese de que los datos enviados a la secuencia que devuelve la propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> están en formato XPS como una secuencia de paquete.</li></ul>|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
