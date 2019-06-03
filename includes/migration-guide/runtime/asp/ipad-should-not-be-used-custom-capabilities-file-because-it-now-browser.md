---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379562"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>No se debe usar IPad en el archivo de funciones personalizado porque ahora es una funcionalidad del explorador

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, iPad es un identificador en el archivo de funciones de explorador de ASP.NET predeterminado, por lo que no se debe usar en un archivo de funciones personalizado.|
|Sugerencia|Si se requieren funciones específicas de iPad, es necesario modificar el comportamiento de iPad estableciéndolas en el refID &quot;IPad&quot; de puerta de enlace predefinido en lugar de mediante la generación de un nuevo id. &quot;IPad&quot; mediante la búsqueda de coincidencias de agente de usuario.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
