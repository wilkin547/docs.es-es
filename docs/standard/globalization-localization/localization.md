---
title: Localización
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 89851c42570f301bee8a3eca744eb5d069347d4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120867"
---
# <a name="localization"></a><span data-ttu-id="371e4-102">Localización</span><span class="sxs-lookup"><span data-stu-id="371e4-102">Localization</span></span>

<span data-ttu-id="371e4-103">La localización es el proceso de traducción de los recursos de una aplicación en versiones localizadas para cada referencia cultural que la aplicación admite.</span><span class="sxs-lookup"><span data-stu-id="371e4-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="371e4-104">Debe continuar con el paso de localización solo después de completar el paso de [revisión de localización](../../../docs/standard/globalization-localization/localizability-review.md) para verificar que la aplicación globalizada está lista para su localización.</span><span class="sxs-lookup"><span data-stu-id="371e4-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>

<span data-ttu-id="371e4-105">Una aplicación que está lista para la localización se divide en dos bloques conceptuales: un bloque que contiene todos los elementos de la interfaz de usuario y otro que contiene código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="371e4-105">An application that is ready for localization is separated into two conceptual blocks: a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="371e4-106">El bloque de la interfaz de usuario contiene solo los elementos localizables de dicha interfaz, como cadenas, mensajes de error, cuadros de diálogo, menús, recursos de objetos incrustados, etc., para la referencia cultural neutra.</span><span class="sxs-lookup"><span data-stu-id="371e4-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="371e4-107">El bloque de código contiene solo el código de la aplicación que usarán todas las referencias culturales admitidas.</span><span class="sxs-lookup"><span data-stu-id="371e4-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="371e4-108">Common Language Runtime admite un modelo de recursos de ensamblado satélite que separa el código ejecutable de una aplicación de sus recursos.</span><span class="sxs-lookup"><span data-stu-id="371e4-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="371e4-109">Para obtener más información sobre la implementación de este modelo, vea [Recursos de .NET](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="371e4-109">For more information about implementing this model, see [Resources in .NET](../../../docs/framework/resources/index.md).</span></span>

<span data-ttu-id="371e4-110">Para cada versión localizada de la aplicación, agregue un nuevo ensamblado satélite que contenga el bloque de la interfaz de usuario localizada traducida en el idioma apropiado para la referencia cultural de destino.</span><span class="sxs-lookup"><span data-stu-id="371e4-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="371e4-111">El bloque de código de todas las referencias culturales debe permanecer igual.</span><span class="sxs-lookup"><span data-stu-id="371e4-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="371e4-112">La combinación de una versión localizada del bloque de interfaz de usuario con el bloque de código produce una versión localizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="371e4-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>

<span data-ttu-id="371e4-113">El Kit de desarrollo de software (SDK) de Windows proporciona el Editor de recursos de Windows Forms (Winres.exe), que permite localizar rápidamente formularios Windows Forms para referencias culturales de destino.</span><span class="sxs-lookup"><span data-stu-id="371e4-113">The Windows Software Development Kit (SDK) supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="371e4-114">Para obtener información sobre el uso de esta herramienta, vea [Winres.exe (Editor de recursos de Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="371e4-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="371e4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="371e4-115">See also</span></span>

- [<span data-ttu-id="371e4-116">Globalización y localización</span><span class="sxs-lookup"><span data-stu-id="371e4-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)
- [<span data-ttu-id="371e4-117">Revisión de localizabilidad</span><span class="sxs-lookup"><span data-stu-id="371e4-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)
- [<span data-ttu-id="371e4-118">Globalización</span><span class="sxs-lookup"><span data-stu-id="371e4-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)
- [<span data-ttu-id="371e4-119">Recursos de aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="371e4-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
