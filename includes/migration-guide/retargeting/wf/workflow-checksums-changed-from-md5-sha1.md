---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614841"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a><span data-ttu-id="8e67f-101">Las sumas de comprobación de flujo de trabajo han cambiado de MD5 a SHA1</span><span class="sxs-lookup"><span data-stu-id="8e67f-101">Workflow checksums changed from MD5 to SHA1</span></span>

#### <a name="details"></a><span data-ttu-id="8e67f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8e67f-102">Details</span></span>

<span data-ttu-id="8e67f-103">Para admitir la depuración con Visual Studio, el tiempo de ejecución de flujo de trabajo genera una suma de comprobación para una instancia de flujo de trabajo mediante un algoritmo de hash.</span><span class="sxs-lookup"><span data-stu-id="8e67f-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow instance using a hashing algorithm.</span></span> <span data-ttu-id="8e67f-104">En .NET Framework 4.6.2 y versiones anteriores, el hash de suma de comprobación de flujo de trabajo usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="8e67f-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="8e67f-105">A partir de .NET Framework 4.7, el algoritmo es SHA1.</span><span class="sxs-lookup"><span data-stu-id="8e67f-105">Starting with the .NET Framework 4.7, the algorithm is SHA1.</span></span> <span data-ttu-id="8e67f-106">Si se han conservado estas sumas de comprobación en el código, serán incompatibles.</span><span class="sxs-lookup"><span data-stu-id="8e67f-106">If your code has persisted these checksums, they will be incompatible.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8e67f-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8e67f-107">Suggestion</span></span>

<span data-ttu-id="8e67f-108">Si el código no puede cargar las instancias de flujo de trabajo debido a un error de suma de comprobación, pruebe a establecer el modificador `AppContext`&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; en true. En el código:</span><span class="sxs-lookup"><span data-stu-id="8e67f-108">If your code is unable to load workflow instances due to a checksum failure, try setting the `AppContext` switch &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; to true.In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

<span data-ttu-id="8e67f-109">O bien, en la configuración:</span><span class="sxs-lookup"><span data-stu-id="8e67f-109">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="8e67f-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="8e67f-110">Name</span></span>    | <span data-ttu-id="8e67f-111">Valor</span><span class="sxs-lookup"><span data-stu-id="8e67f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8e67f-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8e67f-112">Scope</span></span>   | <span data-ttu-id="8e67f-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="8e67f-113">Minor</span></span>       |
| <span data-ttu-id="8e67f-114">Versión</span><span class="sxs-lookup"><span data-stu-id="8e67f-114">Version</span></span> | <span data-ttu-id="8e67f-115">4.7</span><span class="sxs-lookup"><span data-stu-id="8e67f-115">4.7</span></span>         |
| <span data-ttu-id="8e67f-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="8e67f-116">Type</span></span>    | <span data-ttu-id="8e67f-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="8e67f-117">Retargeting</span></span> |
