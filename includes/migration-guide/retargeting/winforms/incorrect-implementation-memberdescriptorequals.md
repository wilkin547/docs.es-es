---
ms.openlocfilehash: 01c0689bbfb102f8f4d9455f9d258e8ea5515d9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859333"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Implementación incorrecta de MemberDescriptor.Equals

|   |   |
|---|---|
|Detalles|En la implementación original del método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> se comparan dos propiedades de cadena diferentes de los objetos comparados: el nombre de la categoría y la cadena de descripción. La solución consiste en comparar la propiedad <xref:System.ComponentModel.MemberDescriptor.Category> del primer objeto con la propiedad <xref:System.ComponentModel.MemberDescriptor.Category> del segundo y la propiedad <xref:System.ComponentModel.MemberDescriptor.Description> del primero con la propiedad <xref:System.ComponentModel.MemberDescriptor.Description> del segundo.|
|Sugerencia|Si la aplicación depende de que <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> a veces devuelva <code>false</code> cuando los descriptores son equivalentes, y el destino es la versión 4.6.2 de .NET Framework o una versión posterior, tiene varias opciones:<ol><li>Realizar cambios de código para comparar los campos <xref:System.ComponentModel.MemberDescriptor.Category> y <xref:System.ComponentModel.MemberDescriptor.Description> de forma manual además de llamar al método <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.</li><li>Excluir este cambio mediante la adición del valor siguiente al archivo app.config:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Si la aplicación está destinada a .NET Framework 4.6.1 o una versión anterior y se ejecuta en .NET Framework 4.6.2 o una versión anterior, y quiere deshabilitar este cambio, puede establecer el modificador de compatibilidad en <code>false</code> mediante la adición del valor siguiente al archivo app.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|
