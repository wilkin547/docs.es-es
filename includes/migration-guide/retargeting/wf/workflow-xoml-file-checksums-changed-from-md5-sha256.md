---
ms.openlocfilehash: f59c9f048bb3cd3f425e36b931302258fcf693f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803440"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a>Las sumas de comprobación del archivo XOML han cambiado de MD5 a SHA256

|   |   |
|---|---|
|Detalles|Cuando se compilan los proyectos de flujo de trabajo que contienen archivos XOML, se incluye una suma de comprobación del contenido del archivo XOML en el código generado como un valor <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> con el fin de admitir la depuración de flujos de trabajo basados en XOML con Visual Studio. En .NET Framework 4.7.2 y versiones anteriores, este hash de suma de comprobación usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS. A partir de .NET Framework 4.8, el algoritmo que se usa es SHA256. Para ser compatible con WorkflowMarkupSourceAttribute.MD5Digest, se usan solo los primeros 16 bytes de la suma de comprobación generada. Esto puede causar problemas durante la depuración. Es posible que deba volver a compilar el proyecto.|
|Sugerencia|Si volver a compilar el proyecto no soluciona el problema, intente establecer el modificador de <code>AppContext</code>&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; como true. En el código:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>O en un archivo de configuración (esto debe estar en el archivo MSBuild.exe.config de MSBuild.exe que está usando):<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.8|
|Tipo|Redestinación|
