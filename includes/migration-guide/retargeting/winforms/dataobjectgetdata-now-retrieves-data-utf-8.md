---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616083"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="3daa2-101">DataObject.GetData ahora recupera los datos como UTF-8</span><span class="sxs-lookup"><span data-stu-id="3daa2-101">DataObject.GetData now retrieves data as UTF-8</span></span>

#### <a name="details"></a><span data-ttu-id="3daa2-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3daa2-102">Details</span></span>

<span data-ttu-id="3daa2-103">Para las aplicaciones que tienen como destino .NET Framework 4 o que se ejecutan en .NET Framework 4.5.1 o versiones anteriores, `DataObject.GetData` recupera los datos con formato HTML como una cadena ASCII.</span><span class="sxs-lookup"><span data-stu-id="3daa2-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, `DataObject.GetData` retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="3daa2-104">Como resultado, los caracteres que no son ASCII (cuyos códigos ASCII son mayores que 0x7F) se representan mediante dos caracteres aleatorios.</span><span class="sxs-lookup"><span data-stu-id="3daa2-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.</span></span><p/><span data-ttu-id="3daa2-105">Para aplicaciones que tienen como destino .NET Framework 4.5 o posterior y que se ejecutan en .NET Framework 4.5.2, `DataObject.GetData` recupera datos con formato HTML como UTF-8, que representa correctamente caracteres mayores que 0x7F.</span><span class="sxs-lookup"><span data-stu-id="3daa2-105">For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, `DataObject.GetData` retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3daa2-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3daa2-106">Suggestion</span></span>

<span data-ttu-id="3daa2-107">Si implementó una solución alternativa para el problema de codificación mediante cadenas con formato HTML (por ejemplo, mediante la codificación explícita de la cadena HTML recuperada del Portapapeles y su transferencia a <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) y va a redestinar la aplicación de la versión 4 a la versión 4.5, esa solución alternativa se debe eliminar. Si por algún motivo se necesita el comportamiento anterior, la aplicación se puede destinar a .NET Framework 4.0 para obtenerlo.</span><span class="sxs-lookup"><span data-stu-id="3daa2-107">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>

| <span data-ttu-id="3daa2-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3daa2-108">Name</span></span>    | <span data-ttu-id="3daa2-109">Valor</span><span class="sxs-lookup"><span data-stu-id="3daa2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3daa2-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3daa2-110">Scope</span></span>   | <span data-ttu-id="3daa2-111">Borde</span><span class="sxs-lookup"><span data-stu-id="3daa2-111">Edge</span></span>        |
| <span data-ttu-id="3daa2-112">Versión</span><span class="sxs-lookup"><span data-stu-id="3daa2-112">Version</span></span> | <span data-ttu-id="3daa2-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="3daa2-113">4.5.2</span></span>       |
| <span data-ttu-id="3daa2-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="3daa2-114">Type</span></span>    | <span data-ttu-id="3daa2-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="3daa2-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3daa2-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3daa2-116">Affected APIs</span></span>

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>
