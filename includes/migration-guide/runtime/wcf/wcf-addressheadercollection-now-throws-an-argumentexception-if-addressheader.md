---
ms.openlocfilehash: 200c22a1b83149d833a083365ebb65d0e80bc31a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497919"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="25b44-101">WCF AddressHeaderCollection ahora inicia una excepción ArgumentException si un elemento addressHeader es NULL</span><span class="sxs-lookup"><span data-stu-id="25b44-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="25b44-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="25b44-102">Details</span></span>

<span data-ttu-id="25b44-103">A partir de .NET Framework 4.7.1, el constructor <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> inicia una excepción <xref:System.ArgumentException> si uno de los elementos es <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="25b44-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="25b44-104">En .NET Framework 4.7 y versiones anteriores no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="25b44-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="25b44-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="25b44-105">Suggestion</span></span>

<span data-ttu-id="25b44-106">Si encuentra problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="25b44-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="25b44-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="25b44-107">Name</span></span>    | <span data-ttu-id="25b44-108">Valor</span><span class="sxs-lookup"><span data-stu-id="25b44-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="25b44-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="25b44-109">Scope</span></span>   |<span data-ttu-id="25b44-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="25b44-110">Minor</span></span>|
|<span data-ttu-id="25b44-111">Versión</span><span class="sxs-lookup"><span data-stu-id="25b44-111">Version</span></span>|<span data-ttu-id="25b44-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="25b44-112">4.7.1</span></span>|
|<span data-ttu-id="25b44-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="25b44-113">Type</span></span>|<span data-ttu-id="25b44-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="25b44-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="25b44-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="25b44-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
