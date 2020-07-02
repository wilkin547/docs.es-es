---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614680"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a><span data-ttu-id="e9bc6-101">Mejoras de accesibilidad de ASP.NET en .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="e9bc6-101">ASP.NET Accessibility Improvements in .NET Framework 4.7.1</span></span>

#### <a name="details"></a><span data-ttu-id="e9bc6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e9bc6-102">Details</span></span>

<span data-ttu-id="e9bc6-103">A partir de .NET Framework 4.7.1, ASP.NET ha mejorado el funcionamiento de los controles web de ASP.NET con la tecnología de accesibilidad en Visual Studio para una mejor compatibilidad con los clientes de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-103">Starting with the .NET Framework 4.7.1, ASP.NET has improved how ASP.NET Web Controls work with accessibility technology in Visual Studio to better support ASP.NET customers.</span></span>  <span data-ttu-id="e9bc6-104">Entre otros, se incluyen los cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9bc6-104">These include the following changes:</span></span>

- <span data-ttu-id="e9bc6-105">Cambios para implementar patrones de accesibilidad de interfaz de usuario que faltan en los controles, como el cuadro de diálogo Agregar campo en el Asistente para vistas de detalles o el cuadro de diálogo Configurar ListView del Asistente de ListView.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-105">Changes to implement missing UI accessibility patterns in controls, like the Add Field dialog in the Details View wizard, or the Configure ListView dialog of the ListView wizard.</span></span>
- <span data-ttu-id="e9bc6-106">Cambios para mejorar la presentación en el modo Contraste alto, como el Editor de campos del elemento de paginación de datos.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-106">Changes to improve the display in High Contrast mode, like the Data Pager Fields Editor.</span></span>
- <span data-ttu-id="e9bc6-107">Cambios para mejorar las experiencias de navegación del teclado para los controles, como el cuadro de diálogo Campos del Asistente para editar campos del elemento de paginación del control DataPager, el cuadro de diálogo Configurar ObjectContext o el cuadro de diálogo Configurar selección de datos del Asistente para configurar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-107">Changes to improve the keyboard navigation experiences for controls, like the Fields dialog in the Edit Pager Fields wizard of the DataPager control, the Configure ObjectContext dialog, or the Configure Data Selection dialog of the Configure Data Source wizard.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e9bc6-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e9bc6-108">Suggestion</span></span>

<span data-ttu-id="e9bc6-109">**Cómo participar o no en estos cambios** Para que el diseñador de Visual Studio se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-109">**How to opt in or out of these changes** In order for the Visual Studio Designer to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="e9bc6-110">La aplicación web se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9bc6-110">The web application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="e9bc6-111">Instalar Visual Studio 2017 15.3 o una versión posterior, que es compatible con las nuevas características de accesibilidad con el modificador siguiente de AppContext de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-111">Install Visual Studio 2017 15.3 or later, which supports the new accessibility features with the following AppContext Switch by default.</span></span>
- <span data-ttu-id="e9bc6-112">No participar en los comportamientos de accesibilidad heredados agregando el modificador de AppContext `Switch.UseLegacyAccessibilityFeatures` a la sección `<runtime>` del archivo devenv.exe.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-112">Opt out of the legacy accessibility behaviors by adding the `Switch.UseLegacyAccessibilityFeatures` AppContext switch to the `<runtime>` section in the devenv.exe.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

<span data-ttu-id="e9bc6-113">En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, y en las que se quiere conservar el comportamiento de accesibilidad heredado, se puede participar en el uso de las características de accesibilidad heredadas si se establece explícitamente este modificador de AppContext en `true`.</span><span class="sxs-lookup"><span data-stu-id="e9bc6-113">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="e9bc6-114">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e9bc6-114">Name</span></span>    | <span data-ttu-id="e9bc6-115">Valor</span><span class="sxs-lookup"><span data-stu-id="e9bc6-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e9bc6-116">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e9bc6-116">Scope</span></span>   | <span data-ttu-id="e9bc6-117">Secundaria</span><span class="sxs-lookup"><span data-stu-id="e9bc6-117">Minor</span></span>       |
| <span data-ttu-id="e9bc6-118">Versión</span><span class="sxs-lookup"><span data-stu-id="e9bc6-118">Version</span></span> | <span data-ttu-id="e9bc6-119">4.7.1</span><span class="sxs-lookup"><span data-stu-id="e9bc6-119">4.7.1</span></span>       |
| <span data-ttu-id="e9bc6-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9bc6-120">Type</span></span>    | <span data-ttu-id="e9bc6-121">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e9bc6-121">Retargeting</span></span> |
