---
ms.openlocfilehash: 086dac69d085d070511fcfd5820bd2644ee4598e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496091"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a><span data-ttu-id="c638a-101">Las sobrecargas de Marshal.SizeOf y Marshal.PtrToStructure interrumpen el código dinámico</span><span class="sxs-lookup"><span data-stu-id="c638a-101">Marshal.SizeOf and Marshal.PtrToStructure overloads break dynamic code</span></span>

#### <a name="details"></a><span data-ttu-id="c638a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c638a-102">Details</span></span>

<span data-ttu-id="c638a-103">A partir de .NET Framework 4.5.1, el enlace dinámico a los métodos <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> o <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (por ejemplo, a través de Windows PowerShell, IronPython o la palabra clave dynamic de C#) puede dar lugar a excepciones <code>MethodInvocationExceptions</code>, ya que se han agregado nuevas sobrecargas de estos métodos que pueden resultar ambiguas para los motores de scripting.</span><span class="sxs-lookup"><span data-stu-id="c638a-103">Beginning in the .NET Framework 4.5.1, dynamically binding to the methods <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>, or <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>, (via Windows PowerShell, IronPython, or the C# dynamic keyword, for example) can result in <code>MethodInvocationExceptions</code> because new overloads of these methods have been added that may be ambiguous to the scripting engines.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c638a-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c638a-104">Suggestion</span></span>

<span data-ttu-id="c638a-105">Actualice los scripts para que indiquen claramente qué sobrecarga se debe usar.</span><span class="sxs-lookup"><span data-stu-id="c638a-105">Update scripts to clearly indicate which overload should be used.</span></span> <span data-ttu-id="c638a-106">Normalmente, puede hacerse convirtiendo de forma explícita los parámetros de tipo del método como <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="c638a-106">This can typically done by explicitly casting the methods' type parameters as <xref:System.Type>.</span></span> <span data-ttu-id="c638a-107">Visite [este vínculo](https://support.microsoft.com/kb/2909958/) para consultar información más detallada y ejemplos de soluciones alternativas para este problema.</span><span class="sxs-lookup"><span data-stu-id="c638a-107">See [this link](https://support.microsoft.com/kb/2909958/) for more detail and examples of how to workaround the issue.</span></span>

| <span data-ttu-id="c638a-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c638a-108">Name</span></span>    | <span data-ttu-id="c638a-109">Valor</span><span class="sxs-lookup"><span data-stu-id="c638a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c638a-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c638a-110">Scope</span></span>   |<span data-ttu-id="c638a-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="c638a-111">Minor</span></span>|
|<span data-ttu-id="c638a-112">Versión</span><span class="sxs-lookup"><span data-stu-id="c638a-112">Version</span></span>|<span data-ttu-id="c638a-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c638a-113">4.5.1</span></span>|
|<span data-ttu-id="c638a-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="c638a-114">Type</span></span>|<span data-ttu-id="c638a-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c638a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c638a-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c638a-116">Affected APIs</span></span>

<span data-ttu-id="c638a-117">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="c638a-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
