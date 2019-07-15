---
ms.openlocfilehash: 97ca78e154eb25e863256e06caa119fe753bc344
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858406"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="3fd6b-101">La revisión ortográfica de WPF en controles habilitados para texto no funcionará en Windows 10 para los idiomas no incluidos en la lista de idiomas de entrada del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="3fd6b-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3fd6b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3fd6b-102">Details</span></span>|<span data-ttu-id="3fd6b-103">Cuando se ejecuta en Windows 10, es posible que el corrector ortográfico no funcione para los controles habilitados para texto de WPF porque las funciones de revisión ortográfica de la plataforma solo están disponibles para los idiomas que aparecen en la lista de idiomas de entrada. En Windows 10, al agregar un idioma a la lista de teclados disponibles, Windows descarga e instala automáticamente un paquete de características previa petición (Feature on Demand, FOD) que proporciona funciones de revisión ortográfica.</span><span class="sxs-lookup"><span data-stu-id="3fd6b-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="3fd6b-104">Al agregar el idioma a la lista de idiomas de entrada, se admitirá el corrector ortográfico.</span><span class="sxs-lookup"><span data-stu-id="3fd6b-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>|
|<span data-ttu-id="3fd6b-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3fd6b-105">Suggestion</span></span>|<span data-ttu-id="3fd6b-106">Tenga en cuenta que el idioma o el texto que se va a revisar se debe agregar como un idioma de entrada para que el corrector ortográfico funcione en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3fd6b-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>|
|<span data-ttu-id="3fd6b-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3fd6b-107">Scope</span></span>|<span data-ttu-id="3fd6b-108">Borde</span><span class="sxs-lookup"><span data-stu-id="3fd6b-108">Edge</span></span>|
|<span data-ttu-id="3fd6b-109">Versión</span><span class="sxs-lookup"><span data-stu-id="3fd6b-109">Version</span></span>|<span data-ttu-id="3fd6b-110">4.6</span><span class="sxs-lookup"><span data-stu-id="3fd6b-110">4.6</span></span>|
|<span data-ttu-id="3fd6b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="3fd6b-111">Type</span></span>|<span data-ttu-id="3fd6b-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3fd6b-112">Runtime</span></span>|

