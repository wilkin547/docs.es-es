---
title: "Localización"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a><span data-ttu-id="cac82-102">Localización</span><span class="sxs-lookup"><span data-stu-id="cac82-102">Localization</span></span>
<span data-ttu-id="cac82-103">Localización es el proceso de traducción de los recursos de la aplicación en las versiones localizadas de cada referencia cultural que admita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cac82-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="cac82-104">Debe continuar con el paso de localización después de completar la [revisión de adaptabilidad](../../../docs/standard/globalization-localization/localizability-review.md) paso para comprobar que la aplicación globalizada está preparada para la localización.</span><span class="sxs-lookup"><span data-stu-id="cac82-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="cac82-105">Una aplicación que está lista para la localización se divide en dos bloques conceptuales, un bloque que contiene todos los elementos de la interfaz de usuario y un bloque que contiene código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="cac82-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="cac82-106">El bloque de la interfaz de usuario contiene solo los elementos de interfaz de usuario localizables, como cadenas, mensajes de error, cuadros de diálogo, menús, recursos de objetos incrustados, y así sucesivamente para la referencia cultural neutra.</span><span class="sxs-lookup"><span data-stu-id="cac82-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="cac82-107">El bloque de código contiene solo el código de la aplicación que va a usar todas las referencias culturales admitidas.</span><span class="sxs-lookup"><span data-stu-id="cac82-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="cac82-108">Common language runtime admite un modelo de recursos de ensamblado satélite que separa el código ejecutable de una aplicación de sus recursos.</span><span class="sxs-lookup"><span data-stu-id="cac82-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="cac82-109">Para obtener más información acerca de cómo implementar este modelo, vea [recursos en aplicaciones de escritorio](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="cac82-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="cac82-110">Para cada versión localizada de la aplicación, agregue un nuevo ensamblado satélite que contiene el bloque de la interfaz de usuario localizada traducida en el idioma apropiado para la referencia cultural de destino.</span><span class="sxs-lookup"><span data-stu-id="cac82-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="cac82-111">El bloque de código para todas las referencias culturales debe permanecer igual.</span><span class="sxs-lookup"><span data-stu-id="cac82-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="cac82-112">La combinación de una versión localizada del bloque de interfaz de usuario con el bloque de código produce una versión localizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cac82-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="cac82-113">El [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] proporciona el Editor de recursos Windows Forms (Winres.exe) que permite localizar rápidamente formularios Windows Forms para las referencias culturales de destino.</span><span class="sxs-lookup"><span data-stu-id="cac82-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="cac82-114">Para obtener información sobre el uso de esta herramienta, consulte [Winres.exe (Editor de recursos de Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cac82-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac82-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cac82-115">See Also</span></span>  
 [<span data-ttu-id="cac82-116">Globalización y localización</span><span class="sxs-lookup"><span data-stu-id="cac82-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="cac82-117">Revisión de localizabilidad</span><span class="sxs-lookup"><span data-stu-id="cac82-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="cac82-118">Globalización</span><span class="sxs-lookup"><span data-stu-id="cac82-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="cac82-119">Recursos de aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="cac82-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
