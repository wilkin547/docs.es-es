---
ms.openlocfilehash: a26b8c8a6315e57e70f4810ac4f5fb7ab4ba9b58
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857252"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a>WCF AddressHeaderCollection ahora inicia una excepción ArgumentException si un elemento addressHeader es NULL

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.7.1, el constructor <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> inicia una excepción <xref:System.ArgumentException> si uno de los elementos es <code>null</code>. En .NET Framework 4.7 y versiones anteriores no se inicia ninguna excepción.|
|Sugerencia|Si encuentra problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.1|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})?displayProperty=nameWithType></li></ul>|

