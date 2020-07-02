---
ms.openlocfilehash: d29be721b50d1c93723b325774a06e86f77dbebf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621386"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="704f0-101">WCF AddressHeaderCollection ahora inicia una excepción ArgumentException si un elemento addressHeader es NULL</span><span class="sxs-lookup"><span data-stu-id="704f0-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="704f0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="704f0-102">Details</span></span>

<span data-ttu-id="704f0-103">A partir de .NET Framework 4.7.1, el constructor <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> inicia una excepción <xref:System.ArgumentException> si uno de los elementos es <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="704f0-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="704f0-104">En .NET Framework 4.7 y versiones anteriores no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="704f0-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="704f0-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="704f0-105">Suggestion</span></span>

<span data-ttu-id="704f0-106">Si encuentra problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="704f0-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="704f0-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="704f0-107">Name</span></span>    | <span data-ttu-id="704f0-108">Valor</span><span class="sxs-lookup"><span data-stu-id="704f0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="704f0-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="704f0-109">Scope</span></span>   |<span data-ttu-id="704f0-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="704f0-110">Minor</span></span>|
|<span data-ttu-id="704f0-111">Versión</span><span class="sxs-lookup"><span data-stu-id="704f0-111">Version</span></span>|<span data-ttu-id="704f0-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="704f0-112">4.7.1</span></span>|
|<span data-ttu-id="704f0-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="704f0-113">Type</span></span>|<span data-ttu-id="704f0-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="704f0-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="704f0-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="704f0-115">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})></li></ul>|
