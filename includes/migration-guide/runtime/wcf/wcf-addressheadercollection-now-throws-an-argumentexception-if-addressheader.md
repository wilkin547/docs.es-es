---
ms.openlocfilehash: 3506653bfc749ae3d8002715ca72ca89de7a681b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "91024842"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="2fb69-101">WCF AddressHeaderCollection ahora inicia una excepción ArgumentException si un elemento addressHeader es NULL</span><span class="sxs-lookup"><span data-stu-id="2fb69-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="2fb69-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="2fb69-102">Details</span></span>

<span data-ttu-id="2fb69-103">A partir de .NET Framework 4.7.1, el constructor <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> inicia una excepción <xref:System.ArgumentException> si uno de los elementos es `null`.</span><span class="sxs-lookup"><span data-stu-id="2fb69-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is `null`.</span></span> <span data-ttu-id="2fb69-104">En .NET Framework 4.7 y versiones anteriores no se inicia ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="2fb69-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2fb69-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="2fb69-105">Suggestion</span></span>

<span data-ttu-id="2fb69-106">Si encuentra problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="2fb69-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="2fb69-107">Name</span><span class="sxs-lookup"><span data-stu-id="2fb69-107">Name</span></span>    | <span data-ttu-id="2fb69-108">Valor</span><span class="sxs-lookup"><span data-stu-id="2fb69-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="2fb69-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="2fb69-109">Scope</span></span>   | <span data-ttu-id="2fb69-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="2fb69-110">Minor</span></span>   |
| <span data-ttu-id="2fb69-111">Versión</span><span class="sxs-lookup"><span data-stu-id="2fb69-111">Version</span></span> | <span data-ttu-id="2fb69-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="2fb69-112">4.7.1</span></span>   |
| <span data-ttu-id="2fb69-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="2fb69-113">Type</span></span>    | <span data-ttu-id="2fb69-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2fb69-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2fb69-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2fb69-115">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
