---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620546"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>No se debe usar IPad en el archivo de funciones personalizado porque ahora es una funcionalidad del explorador

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, iPad es un identificador en el archivo de funciones de explorador de ASP.NET predeterminado, por lo que no se debe usar en un archivo de funciones personalizado.

#### <a name="suggestion"></a>Sugerencia

Si se requieren funciones específicas de iPad, es necesario modificar el comportamiento de iPad estableciéndolas en el refID &quot;IPad&quot; de puerta de enlace predefinido en lugar de mediante la generación de un nuevo id. &quot;IPad&quot; mediante la búsqueda de coincidencias de agente de usuario.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
