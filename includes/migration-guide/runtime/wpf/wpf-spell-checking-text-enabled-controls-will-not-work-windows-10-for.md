---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496868"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="0fa17-101">La revisión ortográfica de WPF en controles habilitados para texto no funcionará en Windows 10 para los idiomas no incluidos en la lista de idiomas de entrada del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0fa17-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

#### <a name="details"></a><span data-ttu-id="0fa17-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0fa17-102">Details</span></span>

<span data-ttu-id="0fa17-103">Cuando se ejecuta en Windows 10, es posible que el corrector ortográfico no funcione para los controles habilitados para texto de WPF porque las funciones de revisión ortográfica de la plataforma solo están disponibles para los idiomas que aparecen en la lista de idiomas de entrada. En Windows 10, al agregar un idioma a la lista de teclados disponibles, Windows descarga e instala automáticamente un paquete de características previa petición (Feature on Demand, FOD) que proporciona funciones de revisión ortográfica.</span><span class="sxs-lookup"><span data-stu-id="0fa17-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="0fa17-104">Al agregar el idioma a la lista de idiomas de entrada, se admitirá el corrector ortográfico.</span><span class="sxs-lookup"><span data-stu-id="0fa17-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0fa17-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0fa17-105">Suggestion</span></span>

<span data-ttu-id="0fa17-106">Tenga en cuenta que el idioma o el texto que se va a revisar se debe agregar como un idioma de entrada para que el corrector ortográfico funcione en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0fa17-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>

| <span data-ttu-id="0fa17-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0fa17-107">Name</span></span>    | <span data-ttu-id="0fa17-108">Valor</span><span class="sxs-lookup"><span data-stu-id="0fa17-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0fa17-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0fa17-109">Scope</span></span>   |<span data-ttu-id="0fa17-110">Borde</span><span class="sxs-lookup"><span data-stu-id="0fa17-110">Edge</span></span>|
|<span data-ttu-id="0fa17-111">Versión</span><span class="sxs-lookup"><span data-stu-id="0fa17-111">Version</span></span>|<span data-ttu-id="0fa17-112">4.6</span><span class="sxs-lookup"><span data-stu-id="0fa17-112">4.6</span></span>|
|<span data-ttu-id="0fa17-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="0fa17-113">Type</span></span>|<span data-ttu-id="0fa17-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0fa17-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0fa17-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0fa17-115">Affected APIs</span></span>

<span data-ttu-id="0fa17-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="0fa17-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
