---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614788"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a><span data-ttu-id="23e71-101">La serialización de los caracteres de control con DataContractJsonSerializer ahora es compatible con ECMAScript V6 y V8</span><span class="sxs-lookup"><span data-stu-id="23e71-101">Serialization of control characters with DataContractJsonSerializer is now compatible with ECMAScript V6 and V8</span></span>

#### <a name="details"></a><span data-ttu-id="23e71-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="23e71-102">Details</span></span>

<span data-ttu-id="23e71-103">En .NET Framework 4.6.2 y versiones anteriores, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> no serializaba algunos caracteres de control especiales, como \b, \f y \t, de una forma que fuera compatible con los estándares ECMAScript V6 y V8.</span><span class="sxs-lookup"><span data-stu-id="23e71-103">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> did not serialize some special control characters, such as \b, \f, and \t, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span> <span data-ttu-id="23e71-104">A partir de .NET Framework 4.7, la serialización de estos caracteres de control es compatible con ECMAScript V6 y V8.</span><span class="sxs-lookup"><span data-stu-id="23e71-104">Starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="23e71-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="23e71-105">Suggestion</span></span>

<span data-ttu-id="23e71-106">Esta característica está habilitada de forma predeterminada para las aplicaciones destinadas a .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="23e71-106">For apps that target the .NET Framework 4.7, this feature is enabled by default.</span></span> <span data-ttu-id="23e71-107">Si no desea este compartimiento, puede rechazar esta característica agregando la siguiente línea a la sección `<runtime>` del archivo app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="23e71-107">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| <span data-ttu-id="23e71-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="23e71-108">Name</span></span>    | <span data-ttu-id="23e71-109">Valor</span><span class="sxs-lookup"><span data-stu-id="23e71-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="23e71-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="23e71-110">Scope</span></span>   | <span data-ttu-id="23e71-111">Borde</span><span class="sxs-lookup"><span data-stu-id="23e71-111">Edge</span></span>        |
| <span data-ttu-id="23e71-112">Versión</span><span class="sxs-lookup"><span data-stu-id="23e71-112">Version</span></span> | <span data-ttu-id="23e71-113">4.7</span><span class="sxs-lookup"><span data-stu-id="23e71-113">4.7</span></span>         |
| <span data-ttu-id="23e71-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="23e71-114">Type</span></span>    | <span data-ttu-id="23e71-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="23e71-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="23e71-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="23e71-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
