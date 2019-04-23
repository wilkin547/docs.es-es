---
ms.openlocfilehash: 6c2c6422ca4d426fcc2ff5827a2387abb5578e3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234834"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>El análisis de System.Uri cumple con las disposiciones de RFC 3987

|   |   |
|---|---|
|Detalles|El análisis de URI se ha modificado de varias formas en .NET Framework 4.5. Pero tenga en cuenta que estos cambios solo afectan al código que tenga como destino .NET Framework 4.5. Si un binario tiene como destino .NET Framework 4.0, se observará el comportamiento anterior. Entre los cambios efectuados en el análisis de URI en .NET Framework 4.5 se incluyen los siguientes:<ul><li>Los análisis de identificadores URI efectuarán comprobaciones de normalización y caracteres conforme a las normas más recientes sobre IRI indicadas en RFC 3987.</li><li>La forma de normalización C de Unicode solo se ejecutará en la sección de host del identificador URI.</li><li>Mailto no válido: Los identificadores URI ahora generarán una excepción.</li><li>Ahora se conservan los puntos finales al final de un segmento de trazado.</li><li>Los identificadores URI de <code>file://</code> no aplican secuencias de escape al carácter <code>?</code>.</li><li>Los caracteres de control Unicode <code>U+0080</code> a <code>U+009F</code> no son compatibles.</li><li>Las secuencias de escape de los caracteres de coma <code>,</code> y <code>%2c</code> no se eliminan automáticamente.</li></ul>|
|Sugerencia|Si es necesario usar la semántica de análisis de URI anterior de .NET Framework 4.0 (lo que no es habitual), se puede usar si se selecciona .NET Framework 4.0 como destino. Esto se puede hacer mediante un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> en el ensamblado, o bien a través de la interfaz de usuario del sistema del proyecto de Visual Studio, en la página "Propiedades del proyecto".|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Uri.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.UriKind)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.Uri,System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li></ul>|
