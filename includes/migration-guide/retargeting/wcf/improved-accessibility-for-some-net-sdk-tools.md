---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614830"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="61304-101">Mejor accesibilidad para algunas herramientas del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="61304-101">Improved accessibility for some .NET SDK tools</span></span>

#### <a name="details"></a><span data-ttu-id="61304-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="61304-102">Details</span></span>

<span data-ttu-id="61304-103">En el SDK de .NET Framework 4.7.1, se han mejorado las herramientas SvcConfigEditor.exe y SvcTraceViewer.exe mediante la corrección de varios problemas de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="61304-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="61304-104">La mayoría eran problemas menores como un nombre sin definir o determinados patrones de automatización de la interfaz de usuario que no se implementaban correctamente.</span><span class="sxs-lookup"><span data-stu-id="61304-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="61304-105">Aunque muchos usuarios no eran conscientes de estos valores incorrectos, los clientes que usan tecnologías de asistencia como lectores de pantalla encontrarán estas herramientas del SDK más accesibles.</span><span class="sxs-lookup"><span data-stu-id="61304-105">While many users wouldn't be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="61304-106">De hecho, estas correcciones cambian algunos comportamientos anteriores, como el orden del foco del teclado. Para obtener todas las correcciones de accesibilidad en estas herramientas, puede agregar lo siguiente al archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="61304-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| <span data-ttu-id="61304-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="61304-107">Name</span></span>    | <span data-ttu-id="61304-108">Valor</span><span class="sxs-lookup"><span data-stu-id="61304-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61304-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="61304-109">Scope</span></span>   | <span data-ttu-id="61304-110">Borde</span><span class="sxs-lookup"><span data-stu-id="61304-110">Edge</span></span>        |
| <span data-ttu-id="61304-111">Versión</span><span class="sxs-lookup"><span data-stu-id="61304-111">Version</span></span> | <span data-ttu-id="61304-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="61304-112">4.7.1</span></span>       |
| <span data-ttu-id="61304-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="61304-113">Type</span></span>    | <span data-ttu-id="61304-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="61304-114">Retargeting</span></span> |
